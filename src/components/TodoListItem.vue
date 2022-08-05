<!-- eslint-disable vue/no-mutating-props -->
<template>
    <div class="box col-md-4 m-auto mb-3 mt-3 p-3">
        <input
            type="checkbox"
            id="completed"
            class="input-checkbox"
            value="completed"
            v-model="todo.completed"
        />
        <span class="todoCheck" @click="todoCheck"> {{ todo.title }}</span>
        <div>
            <button class="btn btn-danger btn-sm">Delete</button>
        </div>
    </div>
</template>

<script>
export default {
    

    props: {
        todo: Object,
    },
    methods:{
        todoCheck(){
            this.completed = !this.completed;
        },
    },

};
</script>

<style scoped>
.box {
    background-color: rgba(101, 194, 194, 0.52);
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-radius: 8px;
}
.input-checkbox {
    width: 1.2em;
    height: 1.2em;
    accent-color: #ba3c6c;
    box-shadow: 0 0 20px #cb71ce;
}
.btn {
    box-shadow: 0 0 15px #ba3c6c;
}
.btn-danger {
    box-shadow: 0 0 15px #5e3cba;
}
.todoCheck{
    cursor: pointer;
}
</style>
