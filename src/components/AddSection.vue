<template>
    <label for="" class="col-md-4">
        <input
            type="text"
            placeholder="Enter a item"
            class="text-input mb-2"
            @keydown.enter="addTodo"
        />
    <button @click="addTodoBtn" class="btn btn-primary btn-sm m-2">Add</button>
    </label>
</template>
<script>

export default{
props: {
    addItem: Function,
},
setup(props){

    const addTodo = (event) => {
        props.addItem(event.target.value)
        event.target.value = ""
    };
    const addTodoBtn = (event) => {
        props.addItem(event.target.previousElementSibling.value)
        event.target.previousElementSibling.value = ""
    };
    
    return {addTodo,addTodoBtn}
}


}

</script>

<style scoped>
.text-input {
    width: 50%;
    border-radius: 5px;
    border: 1px solid rgba(224, 111, 111, 0.466);
    padding: 5px;
    background-color: #b39aa4a3;
    color: #290211bd;
    transition: ease-in-out, width 0.35s ease-in-out;
    box-shadow: 0 0 10px rgb(101, 194, 194);

}
.text-input:focus {
    border: 1px solid #290714;
    width: 80%;
    box-shadow: 0 0 10px #719ece;
    outline: none;
}
.btn-primary {
    box-shadow: 0 0 15px #5e3cba;
}

</style>