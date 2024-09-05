Cannot find module @rollup/rollup-win32-x64-msvc
Title: [VUE]vue3新建项目 - le.li - 博客园

URL Source: https://www.cnblogs.com/leonlipfsj/p/18324371

Markdown Content:
1、基础准备，需要安装npm，配置下载依赖镜像地址。（略）

环境信息

![Image 1](https://img2024.cnblogs.com/blog/918016/202407/918016-20240730012525989-396257707.png)

window7操作系统

2、打开cmd执行初始化命令

npm create vite@latest

依次按照提示输入：

2.1、  输入"y"并敲回车键

2.2、  输入工程名称“demo-vue3”(自定义名称根据实际修改)

提示：安键盘上下键或者左右键，选择是否，根据实际情况选择，并回车

2.3 根据Now run后边的提示依次输入命令行

![Image 2](https://img2024.cnblogs.com/blog/918016/202407/918016-20240725234117240-1233892738.png)

cd demo-vue3  
npm install  
npm run dev

启动成功后，页面访问：

http://localhost:5173/

![Image 3](https://img2024.cnblogs.com/blog/918016/202407/918016-20240730012259971-112188295.png)

页面访问：

http://localhost:5173/

![Image 4](https://img2024.cnblogs.com/blog/918016/202407/918016-20240730012416665-1557093462.png)

以下是启动报错的场景，window7系统

启动报错：

![Image 5](https://img2024.cnblogs.com/blog/918016/202407/918016-20240730003909888-992927621.png)

注意报错提示，已知bug，

Error: Cannot find module @rollup/rollup-win32-x64-msvc. npm has a bug related t  
o optional dependencies (https://github.com/npm/cli/issues/4828). Please try \`np  
m i\` again after removing both package-lock.json and node\_modules directory.

翻译：

getError:找不到模块@rollup/rollup-win32-x64-msvc。npm有一个与可选依赖项相关的bug(https://github.com/npm/cli/issues/4828). 请在删除package-lock.json和node\_modules目录后再次尝试\`npm i\`。

处理：删除package-lock.json和node\_modules目录后再次尝试\`npm i\`。

问题依然未解决，打开

https://github.com/npm/cli/issues/4828

发现有个windows7的解决方式：

![Image 6](https://img2024.cnblogs.com/blog/918016/202407/918016-20240730012846762-1788155638.png)

执行：

npm i rollup@4.18.0 -D -E

问题解决，服务启动成功