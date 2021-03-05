<template>
  <div class="corpo">

    <nav>
      <ul>       
          <li v-for="route in routes">
            <router-link :to="route.path ? route.path : '/'">{{route.titulo}}</router-link>
          </li>
      </ul>
    </nav>

    <transition name="pagina">
      <router-view></router-view>
    </transition>

  </div>
</template>

<script>
import { routes }  from './routes';

export default {
  data() {
    return {
      routes
    }
  }
}
</script>

<style>
  .corpo {
    font-family: Helvetica, sans-serif;
    width: 96%;
    margin: 0 auto;
  }
  .pagina-enter, 
  .pagina-leave-active {
    opacity: 0;
  }
  .pagina-enter-active, 
  .pagina-leave-active {
    transition: opacity .5s;
  }
</style>