<template>
  <div>
    <h1>{{ titulo }}</h1>    
    <ul>
      <li v-for="foto of fotos">
        <img :src="foto.url" :alt="foto.titulo">
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data () {
    return {
      titulo: 'Alurapic',
      fotos: [
        {
          url: 'https://source.unsplash.com/random',
          titulo: 'Unsplash Image'
        },
        {
          url: 'https://source.unsplash.com/random',
          titulo: 'Unsplash Image'
        }
      ]
    }
  }
}
</script>

<style>
  img {
    max-width: 400px;
  }
</style>