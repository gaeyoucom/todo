<template>
    <div class="todo-item" :class="{'is-complete': todo.completed}">
        <p>
            <input type="checkbox" v-on:change="onChage">
            {{ todo.title }}
            <button class="del-button" 
                @click="$emit('del-todo', todo.id)">X</button>
        </p>
    </div>
</template>

<script>
export default {
    props: ['todo'],
    methods: {
        onChage() {
            this.todo.completed = !this.todo.completed
        }
    }
}
</script>

<style scoped>
.todo-item {
    background: #f4f4f4;
    padding: 1px 10px;
    border-bottom: 1px dotted #ccc;
}
.is-complete {
    text-decoration: line-through;
}
.del-button {
    background: #f00;
    color: #fff;
    border: none;
    border-radius: 100px;
    padding: 5px 8px;
    float: right;
    cursor: pointer;
}
</style>