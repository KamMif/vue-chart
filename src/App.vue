<template>
  <div class="container">
    <ChartBlock msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import ChartBlock from './components/chart-block'

export default {
  name: 'App',
  components: {
    ChartBlock
  }
}
</script>

<style>
  #app {
    font-family: 'Roboto', sans-serif;
  }
  .container {
    height: 100vh;
    width: 100vw;
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>
