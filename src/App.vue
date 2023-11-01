<template>
  <h1>To do application</h1>
  <hr />
  <ToDoList
    v-bind:todos="todos"
  />
</template>

<script>
import ToDoList from '@/components/ToDoList.vue'

export default {
  name: 'App',
  components: {
    ToDoList
  },
  data() {
    return {
      todos: [
        { id: 1, title: 'Buy milk', completed: false },
        { id: 2, title: 'Create app', completed: false },
        { id: 3, title: 'Cook dinner', completed: false }
      ]
    }
  },
}
</script>

<style src="@/App.css" />
