<template>
  <Comments />
</template>

<script>
import Comments from './components/Comments.vue'

export default {
  name: 'app',
  components: {
    Comments
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
