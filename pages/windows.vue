<template>
  <div />
</template>

<script>
import Window from '@/components/Window'
import Calc from '@/apps/Calc'
import Vue from 'vue'
export default {
  mounted () {
    const CalcClass = Vue.extend(Calc)
    const instance = new CalcClass()
    instance.$mount()
    this.createWindow(instance.$el)
  },
  methods: {
    createWindow (child) {
      const WindowClass = Vue.extend(Window)
      const instance = new WindowClass()
      instance.$mount()
      instance.$el.querySelector('.appContent').appendChild(child)
      this.$el.appendChild(instance.$el)
    }
  }
}
</script>

<style>
</style>
