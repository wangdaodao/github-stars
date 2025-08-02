---
project: vue-cli-plugin-qiankun
stars: 167
description: 🚀 qiankun plugin for vue-cli
url: https://github.com/F-loat/vue-cli-plugin-qiankun
---

vue-cli-plugin-qiankun
----------------------

> qiankun plugin for vue-cli

### 使用步骤 (Use setup)

1.  创建主应用 (Create master project)

$ vue create master
$ cd master
$ vue add vue-cli-plugin-qiankun --type master

1.  创建子应用 (Create slave project)

$ vue create foo-app
$ cd foo-app
$ vue add vue-cli-plugin-qiankun --type slave --port 8081

1.  配置主应用 (Config master project)

> master/src/App.vue

<script\>
export default {
  name: 'master',
  data () {
    return {
      // ...
      apps: \[
        { name: 'foo-app', entry: '//localhost:8081', container: '#appContainer', activeRule: '/foo-app' }
      \]
    }
  },
  // ...
  methods: {
    // ...
    initQiankun () {
      // ...
      setDefaultMountApp('/foo-app')
      // ...
    }
  }
}
</script\>

1.  运行各项目 (Run each project)

$ cd master
$ yarn serve

$ cd foo-app
$ yarn serve

### 示例 (Examples)

> DEMO

$ cd examples
$ yarn
$ yarn install:all
$ yarn serve:all

### 功能 (Features)

-   修改项目文件引入 qiankun 框架
    
-   注入 qiankun 框架要求的构建配置
    
-   自动配置 `publicPath` 处理资源路径
    

### 致谢 (Acknowledgements)

-   vue-cli Standard Tooling for Vue.js Development.
    
-   qiankun Blazing fast, simple and completed solution for micro frontends.
    
-   single-spa What an awesome meta-framework for micro-frontends!
