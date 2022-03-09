<template>
  <div class="painel">
    <h2 class="painel-titulo" @dblclick="visivel = !visivel">{{ titulo }}</h2> 
    <transition name="painel-fade">
      <div class="painel-conteudo" v-show="visivel">
        <slot></slot>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  props: ['titulo'],
  data() {
    return {
      visivel: true
    }
  }
}
</script>

<style scoped>
  .painel {
    padding: 0 auto;
    border: solid 2px grey;
    display: inline-block;
    margin: 5px;
    width: 200px;
    height: 100%;
    vertical-align: top;
    text-align: center;
  }
  .painel .painel-titulo {
    text-align: center;
    background: rgb(212, 212, 212);
    margin: 0 0 15px 0;
    padding: 10px;
    text-transform: uppercase;
    cursor: pointer;
    user-select: none;
    font-size: 18px;
  }
  .painel-fade-enter, 
  .painel-fade-leave-active {
    opacity: 0;
  }
  .painel-fade-enter-active, 
  .painel-fade-leave-active {
    transition: opacity .5s;
  }
</style>