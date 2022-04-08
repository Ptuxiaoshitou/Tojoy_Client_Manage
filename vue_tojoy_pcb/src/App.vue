<template>
  <div id="app">
    <router-view>
      <div id="nav">

      </div>
    </router-view>
  </div>
</template>

<script>  
import HelloWorld from '../src/components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld, 
  }
}
</script>

<style>
#app{
  height:100vh;
}
</style>
