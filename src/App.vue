<template>
  <WeShare :rounded="true" mediatype="twitter" size="large"/>
</template>

<script>
import WeShare from './components/WeShare.vue'

export default {
  name: 'App',
  components: {
    WeShare
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
