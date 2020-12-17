<template>
  <div class="app">
    <Window app="app" :v-if="IsOpened" />
    <Icon :v-else-if="!IsOpened" :icon="icon" title="title" />
  </div>
</template>

<script>
export default {
  props: {
    app: {
      type: Object,
      required: true
    },
    titile: {
      type: String,
      required: true
    },
    icon: {
      type: String,
      required: true
    }
  },
  data () {
    return {
      isOpened: false
    }
  }
}
</script>

<style>
</style>
