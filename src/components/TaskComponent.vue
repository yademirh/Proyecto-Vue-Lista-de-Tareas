<script setup>

const props = defineProps({
    nombre: {
        type: String,
        default: 'No tengo nombre'
    },
    numero: {
        type: Number
    }
})

const emit = defineEmits([
    'borrarTask'
])

const deleteTask = (numero) => {
    console.log('Borrrar ',numero);
    emit('borrarTask', numero);
}

</script>

<template>
    <div class="flex justify-between mx-auto h-9 px-4 py-2 bg-gray-200 rounded items-center">
       
        {{ props.nombre }}

        <span class="hover:cursor-pointer h-full flex items-center" @click="deleteTask(props.numero)">
            <svg class="text-red-600 hover:text-red-800 duration-100 fill-current h-full" xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 448 512"><!--! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path d="M64 32C28.7 32 0 60.7 0 96V416c0 35.3 28.7 64 64 64H384c35.3 0 64-28.7 64-64V96c0-35.3-28.7-64-64-64H64zm79 143c9.4-9.4 24.6-9.4 33.9 0l47 47 47-47c9.4-9.4 24.6-9.4 33.9 0s9.4 24.6 0 33.9l-47 47 47 47c9.4 9.4 9.4 24.6 0 33.9s-24.6 9.4-33.9 0l-47-47-47 47c-9.4 9.4-24.6 9.4-33.9 0s-9.4-24.6 0-33.9l47-47-47-47c-9.4-9.4-9.4-24.6 0-33.9z"/></svg>
        </span>
    </div>
    
</template>