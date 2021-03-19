<template>
    <div>
        <form @submit.prevent="addTodo">
            <input type="text" 
                v-model="title"
                placeholder="할 일을 입력하세요...">
            <input type="submit" value="등록">
        </form>
    </div>
</template>

<script>
import { v1 as uuid } from 'uuid'

export default {
    data() {
        return {
            title: ''
        }
    },
    methods: {
        addTodo() {
            console.log(uuid())
            const newTodo = {
                id: uuid(),
                title: this.title,
                completed: false
            }
            this.$emit('add-todo', newTodo)
            this.title = ''
        }
    }
}
</script>

<style scoped>
form {
    display: flex;
}
input[type="text"] {
    flex: 10;
    padding: 10px
}
input[type="submit"] {
    flex: 2;
}
</style>