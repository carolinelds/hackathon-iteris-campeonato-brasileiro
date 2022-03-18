<template>
  <v-app>
    
    <AppTopBar />
    <MeuInicio />
    
  </v-app>
</template>

<script>
import MeuInicio from './components/MeuInicio'
import AppTopBar from './components/shared/AppTopBar'

export default {
  name: 'App',
  components: {
    MeuInicio,
    AppTopBar
  }  
};

</script>

<style>

</style>
