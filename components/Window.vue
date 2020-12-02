<template>
  <div
    class="window"
    :style="{top, left, width, height}"
    @mousedown="mouseDown"
  />
</template>

<script>
export default {
  props: {
    width: {
      type: String,
      required: false,
      default: '150px'
    },
    height: {
      type: String,
      required: false,
      default: '200px'
    }
  },
  data: () => {
    return {
      left: '0px',
      top: '100px'
    }
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
    border: black 1px solid;
    position: absolute;
  }
</style>
