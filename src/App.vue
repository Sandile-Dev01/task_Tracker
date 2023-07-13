<template>
  <div class="container">
    <Header @toggle-add-task="toggleAddTask" :showAddTask="showAddTask" />
    <div>
      <AddTask v-if="showAddTask" @add-task="addTask" />
    </div>
    <Tasks
      @toggle-reminder="toggleReminder"
      @delete-task="deleteTask"
      deleteTask
      :tasks="tasks"
    />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Tasks from "./components/Tasks.vue";
import AddTask from "./components/AddTask.vue";

export default {
  name: "App",
  components: {
    Header,
    Tasks,
    AddTask,
  },

  data() {
    return {
      tasks: [],
      showAddTask: false,
    };
  },

  methods: {
    toggleAddTask() {
      this.showAddTask = !this.showAddTask;
    },

    addTask(task) {
      this.tasks = [...this.tasks, task];
    },

    deleteTask(id) {
      this.tasks = this.tasks.filter((task) => task.id !== id);
    },

    toggleReminder(id) {
      this.tasks = this.tasks.map((task) =>
        task.id === id ? { ...task, reminder: !task.reminder } : task
      );
    },
  },

  created() {
    this.tasks = [
      {
        id: 1,
        text: "Doctors Appointment",
        day: "July 20th at 2:30pm",
        reminder: true,
      },
      {
        id: 2,
        text: "Meeting",
        day: "July 21st at 10:30pm",
        reminder: true,
      },
      {
        id: 3,
        text: "Soccer Game",
        day: "July 30 at 1:30pm",
        reminder: false,
      },
    ];
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Nunito&display=swap");

*,
html {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

body {
  font-family: "Nunito", sans-serif;
  display: flex;
  justify-content: center;
}

.container {
  margin-top: 1rem;
  max-width: 500px;
  min-height: 300px;
  border: 1px solid blue;
  padding: 1.5rem;
  border-radius: 5px;
}

.btn {
  display: inline-block;
  background-color: rgb(34, 34, 34);
  padding: 0.5rem 1rem;
  border: none;
  font-family: inherit;
  border-radius: 5px;
  cursor: pointer;

  color: rgb(255, 255, 255);
}
</style>
