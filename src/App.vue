<template>
  <div id="app">
<div class="container">
  <appHeader></appHeader>
</div>
<div class="container">
  <router-view></router-view>
</div>

    <div class="container">
      <div class="row">
        <div class="col-sm-12 col-md-4">

        </div>
      </div>
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
