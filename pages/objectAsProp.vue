<template>
  <header>
    <Children :data="data" />
  </header>
</template>

<script>
export default {
  data () {
    return {
      data: {
        titulo: 'Hola',
        descripcion: 'pasando objeto a travez del DOM'
      }
    }
  }
}
</script>

<style>
</style>
