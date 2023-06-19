<script>
import AppMain from './components/AppMain.vue'
import AppHeader from './components/AppHeader.vue'

export default {
    components:{
      AppMain,
      AppHeader,
    }
  }
</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style>
  *{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }
</style>
