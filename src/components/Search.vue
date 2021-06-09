<template>
  <div class="aeroport">
    <div v-if="airports.length">
      <div v-for="airport in airports" :key="airport" class="pane">
        {{ airport }}
      </div>
    </div>
    <div v-else>
      <div class="pane">E</div>
      <div class="pane">D</div>
      <div class="pane">I</div>
      <div class="pane">M</div>
      <div class="pane">B</div>
      <div class="pane">U</div>
      <div class="pane">R</div>
      <div class="pane">G</div>
      <div class="pane">H</div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["airports"],
  data() {
    return {
      aeroportsBase: ["New York", "Paris", "Miami", "Sydney"],
    };
  },
};
</script>

<style lang="scss" scoped>
body {
  background: #444;
  display: flex;
  justify-content: center;
}
.aeroport {
  text-align: center;
  padding: 2em 0;
  @media only screen and (max-width: 768px) {
    width: 100%;
    display: flex;
    justify-content: center;
  }
}
.pane {
  width: 1em;
  height: 1em;
  display: inline-block;
  margin: 0 auto;
  border-radius: 0.05em;
  border: 0.01em solid #444;
  position: relative;
  background: #222;
  text-align: center;
  line-height: 1;
  font-size: 80px;
  color: #fff;
  font-family: monospace;
  box-shadow: 0px 0.02em 0 #ccc, 0px 0.05em 0 #000;
  text-shadow: -1px -2px 2px rgba(0, 0, 0, 1);
  z-index: 50;
  @media only screen and (max-width: 768px) {
    width: 0.9em;
    height: 0.9em;
    font-size: 35px;
  }
}

/*.pane:before {
  display: block;
  width: 100%;
  height: 0px;
  content: "";
  position: absolute;
  top: 50%;
  left: 0;
  margin: 0 auto;
  margin-left: -.05em;
  border: .05em solid black;
  z-index: -10;
  
}*/

.pane:after {
  position: absolute;
  top: 50%;
  left: 0;
  content: "";
  border-top: 2px solid #000;
  border-bottom: 2px solid rgba(255, 255, 255, 0.3);
  width: 100%;
  height: 0px;
  opacity: 0.8;
  z-index: 10;
  margin-top: -1px;
}
</style>
