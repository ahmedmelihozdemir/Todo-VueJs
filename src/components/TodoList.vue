<template>
    <section>
        <TodoListItem  v-for="todoItem in todoList " :key="todoItem.id" :todo="todoItem"></TodoListItem>

        <SummaryInfo></SummaryInfo>
        <small> There is {{todoLength}} will do todo.</small>

    </section>
</template>

<script lang="ts">
import TodoListItem from "./TodoListItem.vue";
import SummaryInfo from "./SummaryInfo.vue";
import { computed } from 'vue'; 
export default {
    components: {
        TodoListItem,
        SummaryInfo,
    },
    props:{
        todoList: Array, 
    },
    
    setup(props: { todoList: string|unknown[]; }){
        
        const todoLength = computed(()=>{
            return props.todoList.length;
        });


        return {
            todoLength,
        };
    } 

};

</script>

<style scoped>
.finished {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
</style>
