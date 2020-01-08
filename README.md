# @vue/cli 3 升级到 4

## 前提条件

### vue-cli版本

- vue-cli-4 @vue/cli@4.1.2
- vue-cli-3 @vue/cli@3.12.1


## 文件目录比较

### 变化的内容

#### App.vue 

- before
```vue
<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
  </div>
</template>
<style lang="stylus">
#app
  font-family 'Avenir', Helvetica, Arial, sans-serif
  -webkit-font-smoothing antialiased
  -moz-osx-font-smoothing grayscale
  text-align center
  color #2c3e50

#nav
  padding 30px
  a
    font-weight bold
    color #2c3e50
    &.router-link-exact-active
      color #42b983
</style>

```

- after
```
<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style lang="stylus">
#app
  font-family 'Avenir', Helvetica, Arial, sans-serif
  -webkit-font-smoothing antialiased
  -moz-osx-font-smoothing grayscale
  text-align center
  color #2c3e50
  margin-top 60px
</style>
```

样式代码更加简洁

#### src/components/HelloWorld.vue
增加了vuex、vue-router插件的链接

```html
<li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-router" target="_blank" rel="noopener">router</a></li>
<li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-vuex" target="_blank" rel="noopener">vuex</a></li>
```

#### vue-router
v3
```js
src/router.js
```
```js
src/router/index.js
```

#### vuex
v3
```js
src/store.js
```
v4
```js
src/store/index.js
```

#### babel.config.js
v3
```js
module.exports = {
  presets: [
    '@vue/app'
  ]
}
```

v4
```js
module.exports = {
  presets: [
    '@vue/cli-plugin-babel/preset'
  ]
}
```

#### package.json
- core-js 2 升级到 3

增加两个依赖
- @vue/cli-plugin-router
- @vue/cli-plugin-vuex

@vue/cli-xxx 和 @vue/cli-plugin-xxx的版本升级到4.1.x

#### postcss.config.js
v4中删除

### 没有变化的内容

```js
src/views/*
src/public/*
src/assets/logo.png
src/main.js
.browswerslistrc

// 用来规范编辑，需要配合插件 https://juejin.im/post/5b9cba4c6fb9a05cf67a79a4
// https://relign.github.io/%E5%89%8D%E7%AB%AF%E5%B7%A5%E5%85%B7/editor-config/
.editorconfig

.eslintrc.js
.gitignore
README.md
```