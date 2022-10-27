<template>
  <SanityPortal msg="Welcome to Your Vue.js App"/>
  <Hibana/>
</template>

<script>
import SanityPortal from './components/SanityPortal.vue';
import Hibana from '@/components/Hibana';

export default {
  name: 'App',
  components: {
    SanityPortal,
    Hibana
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
