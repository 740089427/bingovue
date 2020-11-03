# bingovue

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).


 参考 https://blog.csdn.net/lifeisaclimb/article/details/105632885

 vue init webpack bingovue

 安装过程选项使用yarn ，不使用测试，不使用端到端测试 

 安装完毕 cd bingovue

 yarn dev    项目可以启动


安装  element-ui 
 yarn add node-gyp   可以不安装
 yarn add element-ui

 在main.js 中 新增import './plugins/element.js' 
 新建 plugins 文件夹 新建 element.js
 写入
 import Vue from 'vue'
import Element from 'element-ui'
import 'element-ui/lib/theme-chalk/index.css'

Vue.use(Element)



在package.json 的 scripts 中添加
"serve": "vue-cli-service serve",

yarn add @vue/cli-service

yarn serve



安装 axios 
yarn add axios


https://github.com/axios/axios
使用axios

新增less 支持
yarn add less -g

产看less 版本 yarn lessc -v

新增 less loader
yarn add less-loader

安装 typescript
yarn add typescript -g


找到 webpack.base.conf.js 文件 修改 resolve  节点下的 extensions 新增 '.ts', '.tsx',

找到 esintrc.js 文件 在 rules 节点里面 新增 
    'import/extensions': ['error', 'always', {
      js: 'never',
      vue: 'never',
      ts: 'never',
      tsx: 'never'
    }],

忽略 ts 后缀


