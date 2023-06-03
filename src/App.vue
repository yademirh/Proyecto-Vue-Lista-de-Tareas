<script setup>
  import TaskComponent from '@/components/TaskComponent.vue';
  import { ref } from 'vue';

  let newTask;

  const tasksList = ref([
    'Levantarse',
    'Cruzar el semáforo sin mirar',
    'Salvese quien pueda'
  ])

  const deleteTaskarray = (index) => {
    // console.log('Kill ', index)
    console.log('Kill ', tasksList)
    tasksList.value.splice(index, 1)
  }

  const addTask = () => {
    tasksList.value.unshift(newTask);  //o tambien .push
    newTask = undefined   
  }
</script>

<template>

  <div class="font-medium border-2 border-[#ededed] shadow-lg mt-[250px] mx-auto w-[450px] px-8 py-5 bg-gray-50 space-y-2 overflow-hidden">
    <h1 class="text-2xl font-bold text-center">Lista de Tareas</h1>
    <div class="rounded-md overflow-hidden h-9  mx-auto flex border-2      border-black">
      <input v-model="newTask" class="w-4/5 outline-none px-2 py-1" type="text" placeholder="Actividad...">
      <span @click="addTask" class="hover:cursor-pointer bg-blue-500 hover:bg-blue-600 duration-100 border-l-2 border-black w-1/5 flex justify-center items-center text-xl " >
        <svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 448 512"><!--! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path d="M256 80c0-17.7-14.3-32-32-32s-32 14.3-32 32V224H48c-17.7 0-32 14.3-32 32s14.3 32 32 32H192V432c0 17.7 14.3 32 32 32s32-14.3 32-32V288H400c17.7 0 32-14.3 32-32s-14.3-32-32-32H256V80z"/></svg></span>
    </div>

    <TaskComponent v-for="(task,index) in tasksList" :key="index" :nombre="task" :numero="index" @borrarTask="deleteTaskarray" />

  </div>



</template>

<style scoped>

</style>
 

 