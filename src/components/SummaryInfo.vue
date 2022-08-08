<template>
    <div class="finished col-md-4 m-auto">
        <small class="ms-2">Finished: {{completed}} </small>
        <small class="me-2">Not Finished: {{unCompleted}} </small>
    </div>
</template>

<script>
import {computed} from 'vue';


export default {

    props:{
        todoList: Array,
    },

    setup(props){
        const completed = computed(()=> props.todoList.filter(i => i.completed).length)
        const unCompleted = computed(()=> props.todoList.filter(i => !i.completed).length)


        return {
            completed,
            unCompleted,
        };
    }



}


</script>

<style scoped>
small {
    color: #6e1537;
}
</style>
