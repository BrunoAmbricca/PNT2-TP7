<template>
  <div class="container-fluid mt-3">
    <div class="jumbotron">
      <div id="app">
        <h1 id="title">PNT2-TP7</h1>
        <br>
        <Navbar/>
        <router-view></router-view>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from './components/navbar-component.vue'

export default {
  name: 'App',
  components: {
    Navbar
  }
}
</script>

<style>
#title{
  text-align: center;
}
</style>
