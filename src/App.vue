<script setup>
import { ref } from 'vue'

const name = ref('Akonkwa Ushindi')
const status = ref('active')
const tasks = ref(['Task one', 'Task two', 'Task three'])
const link = ref('https://google.com')
const newTask = ref('')
const toogleStatus = () => {
  if (status.value === 'active') {
    status.value = 'pending  '
  } else if (status.value === 'pending') {
    status.value = 'inactive'
  } else {
    status.value = 'active'
  }
}
const addTask = () => {
  if (newTask.value.trim() != '') {
    tasks.value.push(newTask)
    newTask.value = ''
  }
}
</script>

<template>
  <h1>{{ name }}</h1>
  <p v-if="status === 'active'">User active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User inactive</p>
  <form @submit.prevent="addTask">
    <label for="newTask">Add task</label>
    <input type="text" id="newTask" name="newTask" v-model="newTask" />
    <button type="submit">Submit</button>
  </form>
  <h3>tasks:</h3>
  <ul>
    <li v-for="(task, i) in tasks" :key="task">{{ i + 1 }}. {{ task }}</li>
  </ul>
  <a :href="link">Click here for Google</a>
  <br />
  <button @click="toogleStatus">Click here for change status</button>
</template>
