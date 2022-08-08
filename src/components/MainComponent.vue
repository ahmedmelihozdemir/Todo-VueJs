<template>
    <div class="container">
        <div class="row">
            <section class="upper-box">
                <AddSection :addItem="addTodo"></AddSection>

                <TodoList
                    @delete-event="deleteItem"
                    :todoList="todoList"
                ></TodoList>
            </section>
        </div>
    </div>
</template>

<script>
import { ref } from "vue";
import AddSection from "@/components/AddSection.vue";
import TodoList from "@/components/TodoList.vue";

export default {
    components: {
        AddSection,
        TodoList,
    },
    setup() {
        const todoList = ref([]);
        const addTodo = (todoText) => {
            todoList.value.push({
                id: new Date().getTime(),
                title: todoText,
            });
        };
        
        const deleteItem = (todo) => {
            todoList.value = todoList.value.filter((item) => item.id !== todo.id);
        };
        return {
            todoList,
            addTodo,
            deleteItem,

        };
    },
};
</script>

<style>
body {
    background-color: #e7f3b565;
}
.upper-box {
    /*  background-color: #e7f3b565; */
    border-radius: 5px;
    padding: 20px;
}
</style>
