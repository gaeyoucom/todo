<template>
    <div id="app">
        <Header />
        <AddItem v-on:add-todo="addTodo"/>
        <Todos :todos="todos" v-on:del-todo="onDelete" />
    </div>
</template>

<script>
import Header from "./components/Header";
import AddItem from "./components/AddItem"
import Todos from "./components/Todos";

export default {
    name: "App",
    components: {
        Header,
        AddItem,
        Todos,
    },
    data() {
        return {
            todos: [
                {
                    id: 1,
                    title: "첫 번째 할 일",
                    completed: false,
                },
                {
                    id: 2,
                    title: "두 번째 할 일",
                    completed: true,
                },
                {
                    id: 3,
                    title: "세 번째 할 일",
                    completed: false,
                },
            ],
        };
    },
    methods: {
        onDelete(id) {
            this.todos = this.todos.filter((todo) => todo.id != id);
        },
        addTodo(newTodo) {
            this.todos.push(newTodo)
        }
    },
};
</script>

<style>
</style>
