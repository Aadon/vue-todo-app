<template>
    <div :key="todo.id" v-for="todo in todos">
        <Todo @delete-todo="$emit('delete-todo', todo.id)" :todo="todo"/>
    </div>
</template>

<script>
import Todo from './Todo.vue';
    export default {
        name: 'Todos',
        props: {
            todos: Array,
        },
        components: {
            Todo,
        },
        emits: ['delete-todo']
    }
</script>

<style scoped>
</style>