<template>
    <div class="container">
        <div class="row">
            <section class="upper-box">
                <AddSection :addItem="addTodo"></AddSection>

                <TodoList :todoList="todoList"></TodoList>
                
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
        const todoList  = ref([]);
        const addTodo = ((todoText) => {
            todoList.value.push({
                id: new Date().getTime(),
                title: todoText,
                
            });
        
        });
        
        return {
            todoList,
            addTodo,
        };
    },
};
</script>

<style>
body{
    background-color: #e7f3b565;

}
.upper-box {
/*  background-color: #e7f3b565; */    
    border-radius: 5px;
    padding: 20px;
}
</style>
