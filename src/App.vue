<template>
  <h1>To do application</h1>
  <hr />
  <ToDoList />
</template>

<script>
import ToDoList from '@/components/ToDoList.vue'

export default {
  name: 'App',
  components: {
    ToDoList
  }
}
</script>

<style src="@/App.css" />
