<template>
    <div>
        <input type="text" v-model="texto" placeholder="Escribe tu mensaje">
        <button @click="enviarMensaje">Enviar</button>
        
    </div>
</template>

<script setup>
//Definimos una prop para recibir el mensaje
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
    emit('enviarMensaje', {id: Date.now(), mensajeUser: props.mensajeUser, text: texto.value});
    texto.value = '';
}

</script>



