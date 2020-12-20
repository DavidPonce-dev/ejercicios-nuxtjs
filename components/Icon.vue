<template>
  <button @dblclick="handleOpen">
    <img src="../assets/Calc/icon.png" alt="">
    <div>
      Calculadora
    </div>
  </button>
</template>

<script>
export default {
  props: {
    open: {
      type: Function,
      required: true
    }
  },
  methods: {
    handleOpen () {
      this.$props.open()
    }
  }
}
</script>

<style scoped>
button img {
    width: 75px;
    height: 50px;
}
</style>
