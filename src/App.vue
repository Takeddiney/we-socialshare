<template>
  <WeShare :rounded="true" mediatype="twitter" size="large" link="https://vuejsnation.com/" body="vue nation website" hashtags="vuejs"/>
  <WeShare :rounded="true" mediatype="facebook" size="large" link="https://vuejsnation.com/"/>
  <WeShare :rounded="true" mediatype="linkedin" size="large" link="https://vuejsnation.com/"/>
  <WeShare :rounded="true" mediatype="whatsapp" size="large" link="https://vuejsnation.com/" body="vue nation website"/>
  <WeShare :rounded="true" mediatype="telegram" size="large" link="https://vuejsnation.com/"/>
  <WeShare :rounded="true" mediatype="weibo" size="large" link="https://vuejsnation.com/"/>
</template>

<script>
import WeShare from './components/WeShare.vue'
export default {
  name: 'App',
  components: {
    WeShare
},    
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
