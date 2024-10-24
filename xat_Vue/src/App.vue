<template>
  <div>
    <h1>Xat entre usuarios</h1>
    <ul>
      <li v-for="mensaje in mensajes" :key="mensaje.id">
        {{ mensaje.mensajeUser }}: {{ mensaje.text }}
      </li>
    </ul>
    <mensaje :mensajeUser="'Usuario1'" @enviarMensaje="nuevoMensaje" />
  </div>
</template>


<script setup>
  import { ref } from 'vue';
  import mensaje from './components/mensaje.vue'

  const mensajes = ref([]);

  const nuevoMensaje = (mensaje) => {
    mensajes.value.push(mensaje)
  }

</script>


<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
