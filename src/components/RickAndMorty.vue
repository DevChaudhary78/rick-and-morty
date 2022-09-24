<template>
  <main>
    <img src="../assets/morty.png" alt="The image of rick and morty" id="anchor">
    <div id="eyes">
      <img src="../assets/eyes.jpg" alt="Just image of eyes" id="eye" style="top: -200px; left: -72px">
      <img src="../assets/eyes.jpg" alt="Just image of eyes" id="eye" style="top: -186px; left: -134px">
      <img src="../assets/eyes.jpg" alt="Just image of eyes" id="eye" style="top: -318px; left: 7px">
      <img src="../assets/eyes.jpg" alt="Just image of eyes" id="eye" style="top: -317px; left: 59px">
    </div>
  </main>
</template>

<script>
export default {
  name: "RickAndMorty"
}
</script>

<style scoped>
main {
  display: grid;
  place-items: center;
  min-height: 100vh;
  position: relative;
}
#eyes, img {
  position: absolute;
}

#eye {
  position: absolute;
  height: 25px;
  width: 25px;
}
</style>