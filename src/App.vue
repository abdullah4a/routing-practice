<template>
  <div id="app">
    <nav-bar :menuTitles="menus"/>
    <router-view/>
  </div>
</template>
<script>
import NavBar from '@/components/NavBar.vue';
import router from '@/router';
export default {
  components:{
    NavBar
  },data(){
    return {menus:undefined}
  },
  created() {
    this.menus=router.getRoutes().map(route=>({name:route.name,path:route.path, title:route.name}))
  },
}
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
