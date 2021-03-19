<template>
    <div>
        <div v-for="(todo, index) in todos" :key="index">
            <TodoItem :todo="todo" 
                v-on:del-todo="$emit('del-todo', todo.id)" />
        </div>
    </div>
</template>

<script>
import TodoItem from './TodoItem'

export default {
    components: {
        TodoItem
    },
    props: ['todos'],
    methods: {
    }
}
</script>