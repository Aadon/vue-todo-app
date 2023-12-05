<template>
    <div>
        <header>
            <h1>{{ title }}</h1>
            <Button @toggle-add-todo="$emit('toggle-add-todo')"
            :text="showAddTodos ? 'Close' : 'Add Todos'"
            :color="showAddTodos ? 'red' : 'green'"
            />
        </header>
    </div>
</template>

<script>
import Button from './Button.vue';
    export default {
        name: 'Header',
        props: {
            title: String,
            showAddTodos: Boolean,
        },
        components: {
            Button,
        },
    }
</script>

<style scoped>
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 70px;
    background: rgba(0, 0, 0, 0.9);
    padding: 28px 20px;
    color: #eee9e9;
}
</style>