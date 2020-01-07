<template>
  <div id="app">
    <World />
    <div class="point"></div>
  </div>
</template>
<script>
import World from '@/components/World'


export default {
  name: 'app',
  components: {
    World
  },
}
</script>

<style lang="scss">
html {
  box-sizing: border-box;
}
*, *:before, *:after {
  box-sizing: inherit;
}

body {
  margin: 0;
  padding: 0;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 10px;
}

#app {
  min-height: 100vh;
  width: 100%;
  background: crimson;

  // TODO: Remove
  position: relative;
}

.point {
  width: 10px;
  height: 10px;
  position: absolute;
  transform-origin: center;
  background: yellow;
  border-radius: 50%;

  top: 0;
  left: 0;

  transform: translate3d(419.109px, 169.780px, 0);
  display: none;
}
</style>
