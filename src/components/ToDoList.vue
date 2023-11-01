<template>
  <ul>
    <ToDoItem 
      v-for="todo of todos"
      v-bind:todo="todo"
    />
  </ul>
</template>

<script>
import ToDoItem from '@/components/ToDoItem.vue'

export default {
  components: {
    ToDoItem
  },
  props: ['todos'],
}
</script>

<style scoped>
ul{
  list-style: none;
  margin: 0;
  padding: 0;
}
</style>