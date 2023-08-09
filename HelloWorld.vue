<template>
  <div>
    <h2><u>My To-Do List</u></h2>
    <div>
      <input v-model="newTodo" placeholder="Add To Do List" />
      <button @click="addTodo">Add</button>
      <ul>
        <li v-for="(todo, index) in todoList" :key="index">{{ todo }}</li>
      </ul>
      <p v-if="todoList.length >= 4">Hebat!</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
      return {
        newTodo: '',
        todoList: []
      };
    },
    methods: {
      addTodo() {
        if (this.newTodo.trim() !== '') {
          this.todoList.push(this.newTodo);
          this.newTodo = ''; // Reset input setelah menambahkan
        }
      },
  },
};
</script>

<style>
body {
  font-size: medium;
  font-family: monospace;
  background-color:darkolivegreen;
  text-align: left;
}
.text {
  text-align: left;
  margin: auto;
  width: 400px;
}

input[type="text"] {
  border: none;
  border-bottom: 2px solid black;
  font-family: monospace;
  outline: 0;
  font-size: 1.3rem;
  padding: 7px 0;
  background: transparent;
}

.form {
  margin-bottom: 15px;
}

button {
  background-color:khaki;
  border: none;
  border-radius: 30px;
  color: black;
  padding: 16px 20px;
  text-decoration: none;
  margin: 4px 2px;
  cursor: pointer;
}
</style>
