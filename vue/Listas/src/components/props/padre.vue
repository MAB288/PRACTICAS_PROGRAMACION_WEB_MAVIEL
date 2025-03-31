<script setup>
import {ref} from 'vue'
import hijo1 from './hijo1.vue'
import hijo2 from './hijo2.vue'



defineProps ({
   msg: String,
})

</script>

<template>
    <div class="conteiner">
        <h1>soy el componente padre</h1>

        <hijo1 class="mt-4" edad="10"/>
        <hijo2 class="mt-4" edad="4"/>
 
    </div>
 
</template>

<style scoped>

.conteiner {
    color: rgb(89, 0, 255);
    display: flex;
    flex-direction: column;
    align-items: center; /* Centra horizontalmente */
    justify-content: flex-start; /* Lo mantiene en la parte superior */
    height: 100vh; /* Opcional: para ocupar toda la pantalla */
    padding-top: 20px; /* Opcional: agrega un pequeño margen superior */
    text-align: center;
}

</style>
