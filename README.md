## vue-next-qiankun

> qiankun plugin for vue-cli

### 使用步骤 (Use setup)

1. 创建主应用 (Create master project)

``` sh
$ vue create master
$ cd master
$ vue add vue-next-qiankun --type master
```

2. 创建子应用 (Create slave project)

``` sh
$ vue create foo-app
$ cd foo-app
$ vue add vue-next-qiankun --type slave --port 8081
```

3. 配置主应用 (Config master project)

> master/src/App.vue

``` vue
<script>
export default {
  name: 'master',
  data () {
    return {
      // ...
      apps: [
        { name: 'foo-app', entry: '//localhost:8081', container: '#appContainer', activeRule: '/foo-app' }
      ]
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
</script>
```

4. 运行各项目 (Run each project)

``` sh
$ cd master
$ yarn serve
```

``` sh
$ cd foo-app
$ yarn serve
```

### 示例 (Examples)

``` sh
$ cd examples
$ yarn
$ yarn install:all
$ yarn serve:all
```

### 功能 (Features)

- 修改项目文件引入 qiankun 框架

- 注入 qiankun 框架要求的构建配置

- 自动配置 `publicPath` 处理资源路径



- [vue-cli](https://github.com/vuejs/vue-cli) Standard Tooling for Vue.js Development.

- [qiankun](https://github.com/umijs/qiankun) Blazing fast, simple and completed solution for micro frontends.

- [single-spa](https://github.com/CanopyTax/single-spa) What an awesome meta-framework for micro-frontends!
