<template>
    <div>
       <h3>
        {{ todo.text }}
        <i @click="$emit('delete-todo', todo.id)" class="fa-sharp fa-solid fa-xmark"></i>
    </h3>
    </div>
</template>

<script>
    export default {
        name: 'Todo',
        props: {
            todo: Object,
        },
    }
</script>

<style scoped>

h3 {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: #e6fceb;
    padding: 16px;
    color: #494747;
    border-radius: 4px;
    text-transform: capitalize;
    margin-bottom: 8px;
}
.fa-sharp {
    color: red;
    font-size: 20px;
    cursor: pointer;
}
input {
    width: 40px;
}
</style>