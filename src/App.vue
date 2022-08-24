<template>
  <div id="app">
    
    <DirectivesPractice/>
  </div>
</template>

<script>
import DirectivesPractice from './components/DirectivesPractice.vue'

export default {
  name: 'App',
  components: {
    DirectivesPractice
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
