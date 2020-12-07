<template>
  <div class="window" :style="{top, left, width, height}">
    <div class="resizer nw" @mousedown="handleResize" />
    <div class="resizer ne" @mousedown="handleResize" />
    <div class="resizer sw" @mousedown="handleResize" />
    <div class="resizer se" @mousedown="handleResize" />
    <div class="bar" @mousedown="handleDrag" />
  </div>
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
      left: '50px',
      top: '100px',
      isResizing: false
    }
  },
  methods: {
    handleDrag (e) {
      let prevX = e.clientX
      let prevY = e.clientY

      const mouseMove = (e) => {
        const newX = prevX - e.clientX
        const newY = prevY - e.clientY
        const rect = this.$el.getBoundingClientRect()

        this.left = rect.left - newX + 'px'
        this.top = rect.top - newY + 'px'

        prevX = e.clientX
        prevY = e.clientY
      }
      const mouseUp = () => {
        window.removeEventListener('mousemove', mouseMove)
        window.removeEventListener('mouseup', mouseUp)
      }
      if (!this.isResizing) {
        window.addEventListener('mousemove', mouseMove)
        window.addEventListener('mouseup', mouseUp)
      }
    },
    handleResize (e) {
      this.isResizing = true
      const vertice = e.target

      let prevX = e.clientX
      let prevY = e.clientY

      const mouseMove = (e) => {
        const rect = this.$el.getBoundingClientRect()

        if (vertice.classList.contains('se')) {
          this.$el.style.width = rect.width - (prevX - e.clientX) + 'px'
          this.$el.style.height = rect.height - (prevY - e.clientY) + 'px'
        } else if (vertice.classList.contains('sw')) {
          this.$el.style.width = rect.width + (prevX - e.clientX) + 'px'
          this.$el.style.height = rect.height - (prevY - e.clientY) + 'px'
          this.$el.style.left = rect.left - (prevX - e.clientX) + 'px'
        } else if (vertice.classList.contains('ne')) {
          this.$el.style.width = rect.width - (prevX - e.clientX) + 'px'
          this.$el.style.height = rect.height + (prevY - e.clientY) + 'px'
          this.$el.style.top = rect.top - (prevY - e.clientY) + 'px'
        } else {
          this.$el.style.width = rect.width + (prevX - e.clientX) + 'px'
          this.$el.style.height = rect.height + (prevY - e.clientY) + 'px'
          this.$el.style.top = rect.top - (prevY - e.clientY) + 'px'
          this.$el.style.left = rect.left - (prevX - e.clientX) + 'px'
        }

        prevX = e.clientX
        prevY = e.clientY
      }
      const mouseUp = () => {
        window.removeEventListener('mousemove', mouseMove)
        window.removeEventListener('mouseup', mouseUp)
        this.isResizing = false
      }
      window.addEventListener('mousemove', mouseMove)
      window.addEventListener('mouseup', mouseUp)
    }
  }
}
</script>

<style scoped>
  .window{
    border: black 1px solid;
    position: absolute;
  }
  .bar{
    height: 20px;
    background-color: brown;
  }
  .resizer{
    position: absolute;
    width: 5px;
    height: 5px;
    border-radius: 5px;
    background: black;
  }
  .resizer.nw{
    top: -1px;
    left: -1px;
    cursor: nw-resize;
  }
  .resizer.ne{
    top: -1px;
    right: -1px;
    cursor: ne-resize;
  }
  .resizer.sw{
    bottom: -1px;
    left: -1px;
    cursor: sw-resize;
  }
  .resizer.se{
    bottom: -1px;
    right: -1px;
    cursor: se-resize;
  }
</style>
