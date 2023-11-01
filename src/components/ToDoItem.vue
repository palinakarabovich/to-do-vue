<template>
  <li>
    <span
      v-bind:class="{done: todo.completed}"
    >
      <input
      type="checkbox"
      @change="todo.completed = !todo.completed"
      />
      <strong>{{ index + 1 }} </strong>
      {{ todo.title }}
    </span>
    <button
      class='button_remove'
      @click="$emit('remove-todo', todo.id)"
    >
      &times;
  </button>
  </li>
</template>

<script>
export default{
  props: ['todo', 'index']
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

span{
  display: flex;
  align-items: flex-start;
  gap: 10px;
}

.button_remove{
  border-radius: 50%;
  background-color:palevioletred;
  border: none;
  color: #fff;
  font-weight: 900;
  cursor: pointer;
  width: 30px;
  height: 30px;
}

.done{
  text-decoration: line-through;
}
</style>