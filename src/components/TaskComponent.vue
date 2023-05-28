<template>
    <h1>To Do App {{fullName}}</h1>
    <input @keyup.enter="addnewTask" ref="txtTask" type="text" v-model="newTask" placeholder="Add a new task">
    <button @click="addnewTask">Add</button>
    <ul>
        <li v-for="(item,index) in todolist" :key="index">
            {{ item }}
            <button id="btnDelete" @click="removeTask(index)">Delete</button>
        </li>
    </ul>
</template>

<script>

export default{
    name:"TaskComponent",
    data(){
        return {
            todolist: [],
            fullName: "Cristiano Ronaldo",
            newTask:""
        }
    },
    methods:{
        addnewTask(){
            console.log("Aquí se agregará la tarea")
            this.todolist.push(this.newTask)
            this.newTask = ""  
            this.$refs.txtTask.focus()
        },
        removeTask(index){
            console.log("El valor de index es: " + index)
            this.todolist.splice(index,1)
        }


    }
}


</script>

<style>
button{
    background-color: green;
    color: white;
}

button:hover{
    background-color: yellow;
    color: darkgray;
}

#btnDelete{
    background: red;
    color: aliceblue;
}

</style>