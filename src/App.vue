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
  @import './styles/General.scss';
</style>
