<template>
  <div id="app">
<div class="container">
  <appHeader></appHeader>
</div>
<div class="container">
  <router-view></router-view>
</div>
  </div>
</template>

<script>
  import Header from './components/Header.vue'
  export default {
 components:{
   appHeader:Header
 }
}
</script>

<style>

</style>
