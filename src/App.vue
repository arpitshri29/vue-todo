<template>
  <div>
    <Todos v-bind:todos="todos"/>
  </div>
</template>

<script>
  import Todos from "./components/Todos";

export default {
  name: 'App',
  components: {
    Todos

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
