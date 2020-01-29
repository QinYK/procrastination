<template>
  <div id="app">
    <!--variant=primary, success, info, warning, danger, dark, or light    -->
    <b-navbar toggleable="lg" type="dark" variant="dark">
      <b-navbar-brand href="#" v-on:click='link("")'>
        <img src="./assets/logo.png"  alt="Kitten">
        主页
      </b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item v-on:click='link("about")'>关于</b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
<!--    <img src="./assets/logo.png">-->
    <router-view/>
  </div>
</template>

<script>
  	import router from './router'
export default {
  name: 'App',
  methods: {
    link(string){
        router.push("/"+string);
      }
    }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
}
</style>
