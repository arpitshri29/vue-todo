<template>
    <div class="todo-item" v-bind:class="{'done':todo.completed}">
        <input type="checkbox" class="mr-5" v-on:change="taskDone">
        {{todo.title}}
        <button v-on:click="$emit('delete-todo', todo.id)"  class="delete">
            <img src="../assets/delete.png" alt="Delete">
        </button>
    </div>
</template>

<script>
    export default {
        name: 'TodoItem',
        props:['todo'],
        methods:{
            taskDone(){
                let check = this.todo;
                check.completed = !check.completed;
                console.log('clicked: ', check.completed)
            }
        }
    }
</script>

<style scoped>
    .todo-item{
        background: #ffffff;
        padding: 20px;
        margin: 10px;
        border-radius: 5px;
        cursor: pointer;
    }

    .mr-5{
        margin-right: 5px;
    }

    .delete{
        float: right;
        border: none;
    }

    .delete img{
        height: 18px;
    }

    .done{
        text-decoration: line-through;
        background: #ecebeb;
    }
</style>