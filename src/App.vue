<script>
export default {
  data(){
    return{
      name: "Akonkwa Ushindi",
      tasks: ['task one', 'task two', 'task three'],
    };
  },
};
</script>

<template>
  <h1>{{ name }}</h1>
  <h3>tasks:</h3>
  <ul>
    <li v-for="task, i in tasks" :key="task">{{i+1}}. {{ task }}</li>
  </ul>
</template>