<template>
    <div class="task-field">
            <div>
                <label>Add Todo</label>
            <input 
            type="text" 
            v-model="text"
            @keyup.enter="saveTodo"
            placeholder="New task.">
            </div>

            <button 
            class="btn-save"
           @click="saveTodo"
            >
            Save Todo
        </button>
    </div>
</template>

<script>
    export default {
        name: 'AddTodo',
        data() {
            return {
                text: '',
            }
        },
        methods: {
            saveTodo() {
                if(!this.text) {
                    alert('Please add a todo.');
                    return
                }
                const newTodo = {
                    id: Math.floor(Math.random() * 10000),
                    text: this.text,
                }
                this.$emit('save-todo', newTodo)
                this.text = '';
            }
        }
    }
</script>
    
<style scoped>
   .task-field {
    text-align: center;
    margin-bottom: 40px;
   }
     label {
        text-align: center;
        display: block;
        margin-bottom: 40px;
        padding: 8px;
        font-size: 22px;
        background-color: #0097ee;
        color: #fff;
        border-radius: 4px;
    }
    input {
        width: 100%;
        background: #e7e5e5;
        margin-bottom: 16px;
        padding: 12px;
        border: 1px solid #0097ee;
        font-size: 18px;
        outline: none;
        border-radius: 8px;
    }
    .btn-save {
        display: inline-block;
        border: none;
        padding: 8px 16px;
        color: #fff;
        font-size: 18px;
        border-radius: 4px;
        margin: 16px auto;
        background-color: #0097ee;
        cursor: pointer;
        transition: all .15s ease-in-out;
    }
    .btn-save:hover {
       background: rgba(9, 78, 218, 0.7)
    }
</style>