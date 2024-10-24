<template>
  <div class="chat-container">
    <h1>Xat entre usuarios</h1>
    <ul class="mensajes-list">
      <li v-for="mensaje in mensajes" :key="mensaje.id" class="mensaje-item">
        <strong>{{ mensaje.mensajeUser }}:</strong> {{ mensaje.text }}
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
  .chat-container {
    max-width: 600px;
    margin: 0 auto;
    padding: 1rem;
    background-color: #f9f9f9;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  }

  h1 {
    text-align: center;
    color: #333;
  }

  .mensajes-list {
    list-style: none;
    padding: 0;
    margin: 1rem 0;
    max-height: 300px;
    overflow-y: auto;
    border: 1px solid #ccc;
    border-radius: 4px;
    background: white;
  }

  .mensaje-item {
    padding: 0.5rem 1rem;
    border-bottom: 1px solid #eee;
  }

  .mensaje-item {
    border-bottom: none;
    color: black;
  }
</style>
