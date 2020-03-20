<template>
    <div>
        <h1>Tareas</h1>
        <input type="text" placeholder="Escribe una tarea" v-model="newTask">
        <button @click="addTask">Añadir</button>
        <input type="search" placeholder="Filtrar por título" v-model="filteredTask">
        <Task
            v-for="(task, index) in filteredTasks"
            :key="task.id"
            :title="task.title"
            @deleteTask="deleteTask(index)"
        />
    </div>
</template>

<script>
import Task from '@/components/Task'

const url = 'https://jsonplaceholder.typicode.com/todos'

export default {
    name: 'Tasks',
    created() {
        fetch(url)
            .then(response => response.json())
                .then(data => this.tasks = data)
            .catch(error => console.error(error))

    },
    data() {
        return {
            newTask: '',
            tasks: [],
            filteredTask: ''
        }
    },
    methods: {
        addTask() {
            this.tasks.unshift({ title: this.newTask })
            this.newTask = ''
        },
        deleteTask(index) {
            this.tasks.splice(index, 1)
        }
    },
    computed: {
        filteredTasks() {
            return this.tasks.filter(task => task.title.includes(this.filteredTask))
        }
    },
    components: {
        Task
    }
}
</script>

<style>

</style>