<template>
  <div>
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:delete-todo="deleteTodo"/>
  </div>
</template>

<script>
  import Todos from "./components/Todos";
  import AddTodo from "./components/AddTodo";

export default {
  name: 'App',
  components: {
    Todos,
    AddTodo
  },
  data(){
    return{
      todos: [
        {
          id: 1,
          title: 'Get milk',
          completed: false
        },
        {
          id: 2,
          title: 'Pay bill',
          completed: false
        },
        {
          id: 3,
          title: 'Buy groceries',
          completed: false
        }
      ]
    }
  },
  methods:{
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id)
    },
    addTodo(newTodo){
      this.todos = [...this.todos, newTodo]
    }
  }
}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    background: aliceblue;
  }

  body{
    font-family: Arial, Helvetica, sans-serif;
  }
</style>
