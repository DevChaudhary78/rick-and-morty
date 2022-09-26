<template>
  <main id="app">
    <RickAndMorty></RickAndMorty>
  </main>
</template>

<script>
import RickAndMorty from './components/RickAndMorty.vue'

export default {
  name: 'App',
  components: {
    RickAndMorty
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: #000;
  color: #fff;
}
</style>
