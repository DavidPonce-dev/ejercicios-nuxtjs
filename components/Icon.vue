<template>
  <div>
    <img class="icon" src="" alt="">
  </div>
</template>

<script>
export default {
  props: {
    titile: {
      type: String,
      required: true
    },
    icon: {
      type: String,
      required: true
    }
  },
  metaInfo () {
    return {
      title: this.title
    }
  }
}
</script>

<style>
.icon {
    width: 50px;
    height: 50px;
}
</style>
