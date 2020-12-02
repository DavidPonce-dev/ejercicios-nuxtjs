<template>
  <div
    class="window"
    :style="{top: top, left: left}"
    @mousedown="mouseDown"
  />
</template>

<script>
// eslint-disable-next-line
import Vue from 'vue'
export default {
  data: () => {
    // eslint-disable-next-line
    let datos = {
      left: '0px',
      top: '100px'
    }
    return datos
  },
  methods: {
    mouseDown (e) {
      let prevX = e.clientX
      let prevY = e.clientY

      const mouseMove = (e) => {
        const newX = prevX - e.clientX
        const newY = prevY - e.clientY
        const rect = this.$el.getBoundingClientRect()

        this.$el.style.left = rect.left - newX + 'px'
        this.$el.style.top = rect.top - newY + 'px'

        prevX = e.clientX
        prevY = e.clientY
      }
      const mouseUp = () => {
        window.removeEventListener('mousemove', mouseMove)
        window.removeEventListener('mouseup', mouseUp)
      }
      window.addEventListener('mousemove', mouseMove)
      window.addEventListener('mouseup', mouseUp)
    }
  }
}
</script>

<style>
  .window{
    width: 300px;
    height: 500px;
    border: black 1px solid;
    position: absolute;
  }
</style>
