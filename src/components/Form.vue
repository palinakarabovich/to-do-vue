<template>
  <form
    @submit.prevent="onSubmit"
  >
  <input
    type="text"
    v-model="title"
  />
  <button
    type="submit"
  >
    Add
  </button>
</form>
</template>

<script>
  export default{
    data(){
      return {
        title: ''
      }
    },
    methods: {
      onSubmit(){
        // return a line without spaces
        if(this.title.trim()){
          const newToDo = {
            id: Date.now(),
            title: this.title,
            completed: false
          }
          this.$emit('add-todo', newToDo)
          this.title = ''
        }
      }
    }
  }
</script>

<style scoped>
form{
  display: flex;
  gap: 10px;
  align-items: center;
  justify-content: center;
  padding: 20px 10px;
}

input{
  width: 400px;
  height: 20px;
  border-radius: 5px;
  border: 1px solid palevioletred;
}

button{
  background-color: transparent;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-weight: 900;
}
</style>