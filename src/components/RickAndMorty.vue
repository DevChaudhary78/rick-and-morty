<template>
  <main>
    <img src="../assets/morty.png" alt="The image of rick and morty" id="anchor">
    <div class="eyes">
      <img src="../assets/eyes.jpg" alt="Just image of eyes" class="eye" style="top: -194px; left: -144px">
      <img src="../assets/eyes.jpg" alt="Just image of eyes" class="eye" style="top: -204px; left: -81px">
      <img src="../assets/eyes.jpg" alt="Just image of eyes" class="eye" style="top: -327px; left: -5px">
      <img src="../assets/eyes.jpg" alt="Just image of eyes" class="eye" style="top: -328px; left: 53px">
    </div>
  </main>
</template>

<script>
//
//const angle = function(cx, cy, ex, ey) {
//  const dy = ey - cy;
//  const dx = ex - cx;
//
//  const rad = Math.atan2(dy, dx);
//  return rad * 180 / Math.PI;
//}
//document.addEventListener("mouseover", (e) => {
//  const mouseX = e.clientX;
//  const mouseY = e.clientY;
//
//  const anchor = document.getElementById('anchor');
//  const rekt = anchor.getBoundingClientRect();
//  const anchorX = rekt.left + rekt.width / 2;
//  const anchorY = rekt.top + rekt.height / 2;
//
//  const eyes = document.querySelectorAll('#eye');
//
//  const angleDeg = angle(mouseX, mouseY, anchorX, anchorY);
//
//  console.log(angleDeg);
//  eyes.forEach(eye => {
//    eye.style.transform = `rotate(${90+angleDeg}deg)`;
//  })
//})

export default {
  name: "RickAndMorty",
  methods: {
    initialize() {
      document.addEventListener("mouseover", (e) => {
        this.mouseX = e.clientX;
        this.mouseY = e.clientY;

        this.angleDeg = this.angle(this.mouseX, this.mouseY, this.anchorX, this.anchorY);

        console.log(this.angleDeg);

        this.eyes.forEach(eye => {
          eye.style.tranform = `rotate(${90+this.angleDeg}deg)`;
          this.anchor.style.filter = `hue-rotate(${this.angleDeg}deg)`;
        })
      })
    },

    angle(cx, cy, ex, ey) {
      const dy = ey - cy;
      const dx = ex - cx;

      const rad = Math.atan2(dy, dx);
      return rad * 180 / Math.PI;
    }
  },
  mounted() {
    this.anchor= document.getElementById('anchor');
    this.rekt= this.anchor.getBoundingClientRect();
    this.anchorX = this.rekt.left + this.rekt.width / 2;
    this.anchorY = this.rekt.top + this.rekt.height / 2;

    this.eyes = document.querySelectorAll('.eye')

    this.initialize();
  }
}
</script>

<style scoped>
main {
  display: grid;
  place-items: center;
  min-height: 100vh;
  position: relative;
}
.eyes, img {
  position: absolute;
}

.eye {
  position: absolute;
  height: 40px;
  width: 40px;
  border-radius: 50%;
}
</style>