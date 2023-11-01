<template>
  <li>
    <span
      v-bind:class="{done: todo.completed}"
    >
      <input type="checkbox" />
      <strong>{{ todo.id }}</strong>
      {{ todo.title }}
    </span>
    <button
      class='button_remove'
    >
      &times;
  </button>
  </li>
</template>

<script>
export default{
  props: ['todo']
}
</script>

<style scoped>
li{
  border: 1px solid #ccc;
  display: flex;
  justify-content: space-between;
  padding: 20px;
  margin: 20px;
  border-radius: 5px;
}

input{
  margin-right: 10px;
}

.button_remove{
  border-radius: 50%;
  background-color:palevioletred;
  border: none;
  color: #fff;
  font-weight: 900;
  cursor: pointer;
}

.done{
  text-decoration: line-through;
}
</style>