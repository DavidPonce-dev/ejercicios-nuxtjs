<template>
  <div>
    <header>
      <h1> {{ titulo }} </h1>
    </header>
    <div>
      <p> {{ descripcion }} </p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    data: {
      type: Object,
      required: true
    }
  },
  data () {
    return {
      titulo: this.$props.data.titulo,
      descripcion: this.$props.data.descripcion
    }
  }
}
</script>

<style>

</style>
