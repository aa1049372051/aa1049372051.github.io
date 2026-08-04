URL Source: http://konnga.cn/vue3-typescript/skills/global.html
vue3 全局变量和全局方法
--------------
vue3 已经抛弃了直接在 `Vue.prototype` 上定义全局属性的方式，而是采用 `app.config.globalProperties` 的方式。
并且，当全局属性和组件属性冲突时，比如命名相同，组件属性的优先级更高。
### 模板中使用
    <template>
      <div>
        作者：{{ getObjChainingVal(data, 'user.info.name') }}
        <div>{{ $website }}</div>
      </div>
    </template>
    

### 组件实例中使用
    <script>
    export default {
      mounted() {
        console.log(this.$website) // 'devcursor'
      }
    }
    </script>
    

### `script setup` 用法
    <script setup>
    import { getCurrentInstance } from 'vue'
    
    const app = getCurrentInstance()
    const website = app.appContext.config.globalProperties.$website
    console.log(website)
    
    // 或者
    const { proxy } = getCurrentInstance()
    console.log(proxy.$website)
    
    // 使用解构赋值
    const { $web } = getCurrentInstance()!.appContext.config.globalProperties
    console.log($web)
    
    </script>
    

警告
全局属性的好处就是一次定义，无需引入即可使用，使用很方便，但请忽滥用全局属性。