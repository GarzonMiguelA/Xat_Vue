<template>
    <div class="mensaje-container">
      <input type="text" v-model="texto" placeholder="Escribe tu mensaje" class="mensaje-input">
      <button @click="enviarMensaje" class="mensaje-button">Enviar</button>
    </div>
  </template>
  


  <script setup>
  import { defineProps, ref, defineEmits } from 'vue';
  
  const props = defineProps({
    mensajeUser: {
      type: String,
      required: true
    }
  });
  
  const emit = defineEmits(['enviarMensaje']);
  const texto = ref('');
  
  const enviarMensaje = () => {
    emit('enviarMensaje', { id: Date.now(), mensajeUser: props.mensajeUser, text: texto.value });
    texto.value = '';
  }
  </script>
  






  <style scoped>
    .mensaje-container {
        display: flex;
        margin-top: 1rem;
    }
    
    .mensaje-input {
        flex: 1;
        padding: 0.5rem;
        border: 1px solid #ccc;
        border-radius: 4px;
        font-size: 1rem;
    }
    
    .mensaje-button {
        padding: 0.5rem 1rem;
        margin-left: 0.5rem;
        background-color: #ff0800;
        color: white;
        border: none;
        border-radius: 4px;
        cursor: pointer;
        font-size: 1rem;
    }
  </style>
  