Title: Node:解决Error: error:0308010C:digital envelope routines::unsupported的四种解决方案-CSDN博客

URL Source: https://blog.csdn.net/a1010256340/article/details/136525419

Markdown Content:
### 问题描述：  
        报错：Error: error:0308010C:digital envelope routines::unsupported

### 报错原因：

主要是因为 nodeJs V17 版本发布了 OpenSSL3.0 对算法和秘钥大小增加了更为严格的限制，nodeJs v17 之前版本没影响，但 V17 和之后版本会出现这个错误。 我的[node版本](https://so.csdn.net/so/search?q=node%E7%89%88%E6%9C%AC&spm=1001.2101.3001.7020)是v18+

报错详细信息：

      error: error:0308010C:digital envelope routines::unsupported        at new Hash (node:internal/crypto/hash:71:19)        at Object.createHash (node:crypto:133:10)        at module.exports (D:\XXX\map-edit2\font\node_modules\webpack\lib\util\createHash.js:135:53)        at NormalModule._initBuildHash (D:\XXX\map-edit2\font\node_modules\webpack\lib\NormalModule.js:417:16)        at handleParseError (D:\XXX\map-edit2\font\node_modules\webpack\lib\NormalModule.js:471:10)        at D:\XXX\map-edit2\font\node_modules\webpack\lib\NormalModule.js:503:5        at D:\XXX\map-edit2\font\node_modules\webpack\lib\NormalModule.js:358:12        at D:\XXX\map-edit2\font\node_modules\loader-runner\lib\LoaderRunner.js:373:3        at iterateNormalLoaders (D:\XXX\map-edit2\font\node_modules\loader-runner\lib\LoaderRunner.js:214:10)        at iterateNormalLoaders (D:\XXX\map-edit2\font\node_modules\loader-runner\lib\LoaderRunner.js:221:10)        at D:\XXX\map-edit2\font\node_modules\loader-runner\lib\LoaderRunner.js:236:3        at runSyncOrAsync (D:\XXX\map-edit2\font\node_modules\loader-runner\lib\LoaderRunner.js:130:11)        at iterateNormalLoaders (D:\XXX\map-edit2\font\node_modules\loader-runner\lib\LoaderRunner.js:232:2)        at Array.<anonymous> (D:\XXX\map-edit2\font\node_modules\loader-runner\lib\LoaderRunner.js:205:4)        at Storage.finished (D:\XXX\map-edit2\font\node_modules\enhanced-resolve\lib\CachedInputFileSystem.js:55:16)        at D:\XXX\map-edit2\font\node_modules\enhanced-resolve\lib\CachedInputFileSystem.js:91:9    node:internal/crypto/hash:71      this[kHandle] = new _Hash(algorithm, xofLen);                      ^    Error: error:0308010C:digital envelope routines::unsupported        at module.exports (D:\XXX\map-edit2\font\node_modules\webpack\lib\util\createHash.js:135:53)        at NormalModule._initBuildHash (D:\XXX\map-edit2\font\node_modules\webpack\lib\NormalModule.js:417:16)        at handleParseError (D:\XXX\map-edit2\font\node_modules\webpack\lib\NormalModule.js:471:10)        at D:\XXX\map-edit2\font\node_modules\webpack\lib\NormalModule.js:503:5        at D:\XXX\map-edit2\font\node_modules\webpack\lib\NormalModule.js:358:12        at D:\XXX\map-edit2\font\node_modules\loader-runner\lib\LoaderRunner.js:373:3        at iterateNormalLoaders (D:\XXX\map-edit2\font\node_modules\loader-runner\lib\LoaderRunner.js:214:10)        at Array.<anonymous> (D:\XXX\map-edit2\font\node_modules\loader-runner\lib\LoaderRunner.js:205:4)        at Storage.finished (D:\XXX\map-edit2\font\node_modules\enhanced-resolve\lib\CachedInputFileSystem.js:55:16)        at D:\XXX\map-edit2\font\node_modules\enhanced-resolve\lib\CachedInputFileSystem.js:91:9        at D:\XXX\map-edit2\font\node_modules\graceful-fs\graceful-fs.js:123:16        at FSReqCallback.readFileAfterClose [as oncomplete] (node:internal/fs/read_file_context:68:3) {      opensslErrorStack: [ 'error:03000086:digital envelope routines::initialization error' ],      library: 'digital envelope routines',      reason: 'unsupported',      code: 'ERR_OSSL_EVP_UNSUPPORTED'    }    Node.js v18.12.1

### 解决方案:

方案1：打开IDEA 终端，直接输入

Linux & Mac OS：

    export NODE_OPTIONS=--openssl-legacy-provider

Windows：

    set NODE_OPTIONS=--openssl-legacy-provider

方案2：打开IDEA 终端，直接输入（问题解决）

    $env:NODE_OPTIONS="--openssl-legacy-provider"

方案3:卸载当前版本，安装合适的版本(node.js)

方案4:

解决方式（仅限 windows）:

在项目中 package.json 的 scripts 中新增 SET NODE\_OPTIONS=--openssl-legacy-provider

添加前：

    "scripts": {"dev": "vue-cli-service serve","build:prod": "vue-cli-service build"    },

添加后:

    "scripts": {"dev": "SET NODE_OPTIONS=--openssl-legacy-provider && vue-cli-service serve","build:prod": "SET NODE_OPTIONS=--openssl-legacy-provider && vue-cli-service build"    },

笔者本人是采用第四种方案解决的，大家可以试试，希望可以帮到大家。