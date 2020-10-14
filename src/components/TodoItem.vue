<template>
    <div class="todo-item" v-bind:class="{'done':todo.completed}">
        <input type="checkbox" class="mr-5" v-on:change="taskDone">
        {{todo.title}}
    </div>
</template>

<script>
    export default {
        name: 'TodoItem',
        props:['todo'],
        methods:{
            taskDone(){
                console.log('Task completed!');
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

    .done{
        text-decoration: line-through;
        background: #ecebeb;
    }
</style>