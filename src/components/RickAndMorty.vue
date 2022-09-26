<template>
  <main>
    <img src="../assets/morty.png" alt="The image of rick and morty" id="anchor">
    <div class="eyes">
      <img src="../assets/eyes.jpg" alt="Just image of eyes" class="eye" style="top: -157px; left: -118px">
      <img src="../assets/eyes.jpg" alt="Just image of eyes" class="eye" style="top: -166px; left: -68px">
      <img src="../assets/eyes.jpg" alt="Just image of eyes" class="eye" style="top: -265px; left: -6px">
      <img src="../assets/eyes.jpg" alt="Just image of eyes" class="eye" style="top: -267px; left: 38px">
    </div>
  </main>
</template>

<script>
export default {
  name: "RickAndMorty",
  methods: {
    initialize() {
      document.addEventListener("mouseover", (e) => {
        this.mouseX = e.clientX;
        this.mouseY = e.clientY;

        this.angleDeg = this.angle(this.mouseX, this.mouseY, this.anchorX, this.anchorY);

        this.eyes.forEach(eye => {
          eye.style.transform = `rotate(${90+this.angleDeg}deg)`;
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

#anchor {
  height: 80vh;
}

.eye {
  position: absolute;
  height: 35px;
  width: 35px;
  border-radius: 50%;
}
</style>