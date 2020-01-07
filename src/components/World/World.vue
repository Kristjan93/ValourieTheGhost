<template>
  <div class="world">
    <div class="ghost-container">
      <Ghost class="ghost" />
      <Shadow />
    </div>
  </div>
</template>

<script>
import Ghost from '@/components/Ghost'
import Shadow from '@/components/Shadow'

export default {
  components: {
    Ghost,
    Shadow
  },
  methods: {
    moveGhostEyes(clickEvent) {
      const ghostClientRect = document.querySelector('#Vector_2').getBoundingClientRect()

      // Create the triangle so we can calculate the degrees.
      // We need to use that sweet sweet "Law of Cosines 👻.
      const A = {
        x: ghostClientRect.left + ghostClientRect.width / 2,
        y: ghostClientRect.top + ghostClientRect.height / 2
      }

      const B = {
        x: ghostClientRect.left + ghostClientRect.width / 2,
        y: ghostClientRect.top
      }

      const C = {
        x: clickEvent.clientX,
        y: clickEvent.clientY
      }

      const c = ghostClientRect.height / 2
      const b = Math.hypot(C.x - A.x, C.y - A.y)
      const a = Math.hypot(C.x - B.x, C.y - B.y)
      //x=417&y=183 click
      let rotationOfEye = Math.acos( (b*b + c*c - a*a ) / (2*b*c) ) * (180/Math.PI);
      rotationOfEye = C.x > A.x ? rotationOfEye : rotationOfEye * -1

      document.querySelector('#Vector_2').style.transform = `rotate(${-135 + rotationOfEye}deg)`
      document.querySelector('#Vector_2').getBoundingClientRect()
    }
  },
  mounted() {
    const self = this;
    window.addEventListener("click", function(event) {
      // screenX: 683
      // screenY: 598
      // clientX: 683
      // clientY: 486
      self.moveGhostEyes(event)
    })
  }
}
</script>

<style lang="scss" scoped>
.world {
  display: flex;
  justify-content: center;
  padding-top: 100px;

  .ghost-container {
    display: flex;
    flex-direction: column;
    justify-content: center;

    .ghost {
      margin-bottom: 24px;
    }
  }
}
</style>