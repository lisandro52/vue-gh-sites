<template>
  <div id="app" class="content">
    <p>
      <router-link to="/about">About</router-link>
    </p>
    <p>
      <router-link to="/contact">Contact</router-link>
    </p>
    <router-view></router-view>
  </div>
</template>

<script>
  import VueRouter from 'vue-router'
  import MDLoader from './components/MDLoader.vue'

  const routes = [
    { path: '/:page', component: MDLoader }
  ]

  const router = new VueRouter({
    mode: 'history',
    routes
  })

  export default {
    router
  }

</script>

<style>
  @import '../node_modules/bulma/css/bulma.css';
</style>
