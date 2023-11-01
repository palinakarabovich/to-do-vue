<template>
  <h1>To do application</h1>
  <hr />
  <Form 
    @add-todo="addToDo"
  />
  <ToDoList
    v-bind:todos="todos"
    @remove-todo="removeToDo"
  />
</template>

<script>
import ToDoList from '@/components/ToDoList.vue'
import Form from '@/components/Form.vue'

export default {
  name: 'App',
  components: {
    ToDoList,
    Form
  },
  data() {
    return {
      todos: []
    }
  },
  mounted(){
    fetch('https://jsonplaceholder.typicode.com/todos?_limit=3')
      .then(response => response.json())
      .then(json => this.todos = json)
  },
  methods: {
    removeToDo(id) {
      this.todos = this.todos.filter((td) => td.id !== id)
    },
    addToDo(todo){
      this.todos.push(todo);
    }
  }
}
</script>

<style src="@/App.css" />
