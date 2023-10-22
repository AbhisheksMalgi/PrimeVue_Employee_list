<template>
  <div class="container">
    <Homeview @toggle-add="toggleAdd" title="Employee list" :showAdd="showAdd" />
    <div v-show="showAdd">
      <AddTask @add-task="addTask" />
    </div>
    <Tasks @toggle-active="toggle - Active" @delete-task="deleteTask" :tasks="tasks" />
  </div>
</template>

<script>
import Homeview from './components/Homeview.vue';
import Tasks from './components/Tasks.vue';
import AddTask from './components/AddTask.vue';
export default {
  name: "App",
  components: {
    Homeview,
    Tasks,
    AddTask,
  },
  data() {
    return {
      tasks: [],
      showAdd: false,
    }
  },
  methods: {
    toggleAdd() {
      this.showAdd = !this.showAdd
    },
    addTask(task) {
      this.tasks = [...this.tasks, task]
    },
    deleteTask(id) {
      if (confirm('Are you sure?')) {
        this.tasks = this.tasks.filter((task) => task.id !== id)
      }
    },
    toggleActive(id) {
      this.tasks = this.tasks.map((task) => task.id === id ? { ...task, active: !task.active } : task)
    },
  },
  created() {
    this.tasks = [
      {
        id: 100,
        active: true,
        firstName: 'Vikram',
        lastName: 'A L',
        department: 'Software Developer',
        info: 'About text snippet sit amet ...',
        skills: [
          "java",
          "react"
        ]
      },
      {
        id: 101,
        active: false,
        department: 'Software Developer',
        firstName: 'Test',
        lastName: 'One',
        info: 'About text snippet sit amet ...',
        skills: [
          "java",
          "react"
        ]
      },
      {
        id: 102,
        active: true,
        department: 'Software Developer',
        firstName: 'Test',
        lastName: 'Two',
        info: 'About text snippet sit amet ...',
        skills: [
          "java",
          "react"
        ]
      },
      {
        id: 103,
        active: false,
        department: 'Software Developer engineer',
        firstName: 'Test edit',
        lastName: 'Three edited',
        info: 'About text snippet sit amet ... kjncsdnno',
        skills: [
          "java",
          "react",
          "javascript"
        ]
      }
    ]
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'poppins', sans-serif;
}

.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}

.btn {
  display: inline-block;
  background: #000;
  Color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}

.btn:focus {
  outline: none;
}

.btn:active {
  transform: scale(0.98);
}

.btn-block {
  display: block;
  width: 100%;
}
</style>