<template>
    <div>
        <button @click="handleClick" :style="{ backgroundColor: color }" class="btn">{{ text }}</button>
    </div>
</template>

<script>
    export default {
        name: 'Button',
        props: {
            text: String,
            color: String
        },
        methods: {
            handleClick() {
                this.$emit('toggle-add-todo')
            }
        }
    }
</script>

<style scoped>
    .btn {
        border: none;
        padding: 8px 16px;
        color: #fff;
        font-size: 16px;
        border-radius: 4px;
        cursor: pointer;
    }
    
</style>