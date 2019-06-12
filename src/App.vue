<template>
  <div id="app">
    <Header />
    <index />
  </div>
</template>

<script>
import Header from './components/Header'
import index from './components/index'

export default {
  name: 'App',
  components: {
    Header,
    index
  }
}
</script>

<style>
#app {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #faf3f9;
}
</style>
