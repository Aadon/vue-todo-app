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
    background: #e6fceb;
    padding: 16px 20px;
    color: #575151;
}
</style>