<template>
<div class="p-[50px]">

  <form @submit.prevent="addTask">
    <input type="text" placeholder="New Task" class="border-1 ring-0 p-[5px] rounded-l" v-model="newTask">
    <button type="submit" class="bg-teal-500 text-white p-[6px] rounded-r cursor-pointer">Add Task</button>
  </form>

<h2 class="text-[30px]">Task List</h2>
<p class="text-[20px]" v-for="(task, index) in tasks">{{ index+1 }}. {{ task }} <span @click="removeTask(index)" class="bg-red-500 w-[20px] h-[20px] text-center leading-[15px] rounded cursor-pointer text-white inline-block">x</span></p>
</div>
</template>

<script  setup>
import { ref, onMounted(() => {  }), } from 'vue';


const newTask =ref('');
const tasks = ref(['task1','task2','task3']);


const addTask =()=>{
  tasks.value.push(newTask.value)
};
const removeTask =(index)=>{
  tasks.value.splice(index,1)
};

onMounted(async() => {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/todos')//await keyword tells the page to wait untile the data processing is finished
  } 
  catch (error) {
    console.log('Warning!!');
  }
}),

</script>