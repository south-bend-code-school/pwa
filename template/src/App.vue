<template>
  <div id="app">
    <header>
      <span>Vue.js PWA</span>
    </header>
    <main>
      <img src="./assets/logo.png" alt="Vue.js PWA">
      {{#router}}
      <router-view></router-view>
      {{else}}
      <hello></hello>
      {{/router}}
    </main>
  </div>
</template>

{{#typescript}}<!-- For *.vue files, <script>'s  need to have a lang="ts" -->{{/typescript}}
<script {{#typescript}}lang="ts"{{/typescript}}>
{{#typescript}}
import Vue from 'vue'{{#if_eq lintConfig "airbnb"}};{{/if_eq}}
import Component from 'vue-class-component'{{#if_eq lintConfig "airbnb"}};{{/if_eq}}
{{/typescript}}
{{#unless router}}
import Hello from './components/Hello{{#typescript}}.vue{{/typescript}}'{{#if_eq lintConfig "airbnb"}};{{/if_eq}}

{{/unless}}
{{#typescript}}
@Component{{#unless router}}({
  components: {
    'hello': Hello
  }
}){{/unless}}
export default class App extends Vue{{else}}
export default{{/typescript}}
  name{{#typescript}} ={{else}}:{{/typescript}} 'app'{{#router}}{{#if_eq lintConfig "airbnb"}},{{/if_eq}}{{else}}{{#unless typescript}}
  components: {
    Hello{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
  }{{#if_eq lintConfig "airbnb"}},{{/if_eq}}{{/unless}}{{/router}}
}{{#if_eq lintConfig "airbnb"}};{{/if_eq}}
</script>

<style>
body {
  margin: 0;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

main {
  text-align: center;
  margin-top: 40px;
}

header {
  margin: 0;
  height: 56px;
  padding: 0 16px 0 24px;
  background-color: #35495E;
  color: #ffffff;
}

header span {
  display: block;
  position: relative;
  font-size: 20px;
  line-height: 1;
  letter-spacing: .02em;
  font-weight: 400;
  box-sizing: border-box;
  padding-top: 16px;
}
</style>
