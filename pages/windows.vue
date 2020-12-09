<template>
  <div />
</template>

<script>
import Window from '@/components/Window'
import Vue from 'vue'
export default {
  mounted () {
    this.addWindow()
  },
  methods: {
    addWindow () {
      const WindowClass = Vue.extend(Window)
      const instance = new WindowClass({ top: '200px' })
      instance.$mount() // pass nothing
      this.$el.appendChild(instance.$el)
    }
  }
}
</script>

<style>
</style>
