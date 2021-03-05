<template>
  <div id="app">
    <Card />
  </div>
</template>

<script>
import Card from '@/components/Card.vue';
export default {
  name: 'App',
  components: {
    Card,
  },
};
</script>

<style>
* {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  padding: 20px;
}
</style>
