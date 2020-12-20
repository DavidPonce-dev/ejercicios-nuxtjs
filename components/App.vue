<template>
  <div class="app">
    <Window v-if="isOpen" :close="close" />
    <Icon v-else :open="open" />
  </div>
</template>

<script>
/* eslint-disable */
export default {
  props:{
  },
  data () {
    return {
      isOpen: true
    }
  },
  methods: {
    close () {
      this.isOpen = false
    },
    open () {
      this.isOpen = true
    }
  }
}
</script>

<style>
</style>
