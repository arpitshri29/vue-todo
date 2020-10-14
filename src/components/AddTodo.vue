<template>
    <div>
        <form v-on:submit="addTodo">
            <input
                    type="text"
                    name="title"
                    placeholder="Add todo"
                    v-model="title"
            >
            <input type="submit" value="Add">
        </form>
    </div>
</template>

<script>
    import { v4 as uuidv4 } from 'uuid';

    export default {
        name: 'AddTodo',
        data(){
            return{
                title:''
            }
        },
        methods:{
            addTodo(e){
                e.preventDefault();
                const newTodo = {
                    id: uuidv4(),
                    title: this.title,
                    completed: false
                };

                this.$emit('add-todo', newTodo);

                this.title = '';
            }
        },
    }
</script>

<style scoped>

    form{
        display: flex;
        padding: 10px;
    }

    input[type='text']{
        flex: 8;
        border: none;
        background-color: rgba(255, 255, 255, .5);
        padding: 15px;
        border-radius: 5px;
    }

    input[type='submit']{
        flex: 2;
        border: none;
        background-color: rgba(67, 195, 113, 0.5);
        border-radius: 5px;
    }
</style>