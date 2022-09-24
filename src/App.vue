<template>
  <main>
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
body {
  background: #000;
  color: #fff;
  padding: 0;
  margin: 0;
}

</style>
