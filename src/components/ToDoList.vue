<!-- v-on: = @ -->

<template>
  <ul>
    <ToDoItem 
      v-for="(todo, i) of todos"
      v-bind:todo="todo"
      v-bind:index="i"
      @remove-todo="removeToDo"
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
  methods: {
    removeToDo(id){
      this.$emit('remove-todo', id)
    }
  }
}
</script>

<style scoped>
ul{
  list-style: none;
  margin: 0 auto;
  padding: 0;
  width: 50%;
}
</style>