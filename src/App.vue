<template>
  <div>
    <h1>{{ titulo }}</h1>
    <img :src="foto.url" :alt="foto.titulo">
  </div>
</template>

<script>
export default {
  data () {
    return {
      titulo: 'Alurapic',
      foto: {
        url: 'https://source.unsplash.com/random',
        titulo: 'Unsplash Image'
      }
    }
  }
}
</script>

<style>

</style>