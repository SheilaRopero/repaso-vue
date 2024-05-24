<script setup>
import { ref } from 'vue';

const notas = ref(['Nota 1','Nota 2','Nota 3','Nota 4','Nota 5','Nota 6'])
const vista = ref('bloque')

function cambiarVista(tipoVista) {
     vista.value = tipoVista;
}
</script>

<template>
    <div >
        <!-- Botones para alternar entre vistas -->

        <div class="flex justify-between pl-20 pr-20 pt-6 pb-6 text-blue-500 bg-blue-300">
            <button @click="cambiarVista('bloque')" class="btn">Vista en bloque</button>
            <button @click="cambiarVista('lista')" class="btn">Vista en lista</button>
        </div>

        <!-- Vista en bloques -->
        <div v-if="vista === 'bloque'" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 p-4">
            <div v-for="nota in notas" :key="nota" class="p-4 bg-white rounded shadow">
                <h2 class="text-xl font-bold">{{ nota }}</h2>
            </div>
        </div>

        <!-- Vista en lista -->
        <div v-else class="space-y-4 p-4">
            <div v-for="nota in notas" :key="nota" class="p-4 bg-white rounded shadow">
                <h2 class="text-xl font-bold">{{ nota }}</h2>
            </div>
        </div>
    </div>
</template>