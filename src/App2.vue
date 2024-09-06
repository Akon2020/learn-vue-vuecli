<script>
export default {
  data() {
    return {
      name: 'Akonkwa Ushindi',
      status: 'active',
      tasks: ['task one', 'task two', 'task three'],
      link: 'https://google.com'
    }
  },
  methods: {
    toogleStatus() {
      if (this.status === 'active') {
        this.status = 'pending  '
      } else if (this.status === 'pending') {
        this.status = 'inactive'
      } else {
        this.status = 'active'
      }
    }
  }
}
</script>

<template>
  <h1>{{ name }}</h1>
  <p v-if="status === 'active'">User active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User inactive</p>
  <h3>tasks:</h3>
  <ul>
    <li v-for="(task, i) in tasks" :key="task">{{ i + 1 }}. {{ task }}</li>
  </ul>
  <a :href="link">Click here for Google</a>
  <br>
  <button @click="toogleStatus">Click here for change status</button>
</template>
