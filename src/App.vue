
<template>
  <h2>Name: {{ name }}</h2>
  <p>Status: {{ status }}</p>
  <button @click="toggleStatus">Change Status</button>

  <br><br>

  <form @submit.prevent="addTask">
    <input type="text" placeholder="Task Name" v-model="newTask">
    <button type="submit">Add Task</button>
  </form>

  <ul>
    <li v-for="(task, index) in tasks" @click="removeTask(index)">{{ task }}</li>
  </ul>
</template>




<!-- Composition Api  -->
<script setup>
import {ref} from 'vue'

const name= ref('Sibgatullah');
const status= ref('pending');
const tasks = ref(['task1','task2','task3']);
const newTask=ref("");

const toggleStatus = () => { //Method for toggle-->
  if(status.value === 'active'){
    status.value= 'pending';
  }
  else if(status.value === 'pending'){
    status.value = 'inactive';
  }
  else{
    status.value='active';
  }
}

const addTask =()=>{//Add task method
  tasks.value.push(newTask.value);
  newTask.value = '';
}

const removeTask =(index)=>{//Delete task method while clicking on task 
  tasks.value.splice(index,1);
  newTask.value = '';
}

</script>
