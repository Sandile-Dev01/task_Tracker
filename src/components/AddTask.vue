<template>
  <form @submit="onSubmit" class="add-form">
    <div class="form-control">
      <label for="">Task</label>
      <input type="text" v-model="text" name="text" placeholder="Add Task" />
    </div>

    <div class="form-control">
      <label for="">Day & Time</label>
      <input
        type="text"
        v-model="day"
        name="day"
        placeholder="Add Day & Time"
      />
    </div>

    <div class="form-control form-control-check">
      <label for="">Set Reminder</label>
      <input v-model="reminder" type="checkbox" name="reminder" />
    </div>

    <input type="submit" value="Save Task" class="btn btn-block" />
  </form>
</template>

<script>
export default {
  name: "AddTask",
  data() {
    return {
      text: "",
      day: "",
      reminder: false,
    };
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();

      if (!this.text) {
        alert("Please add a task");
      }

      const newTask = {
        id: Math.floor(Math.random() * 715),
        text: this.text,
        day: this.day,
        reminder: this.reminder,
      };

      this.$emit("add-task", newTask);

      this.text = "";
      this.day = "";
      this.reminder = false;
    },
  },
};
</script>

<style scoped>
.add-form {
  margin-bottom: 2rem;
  animation: zoomIn 250ms ease-in-out;
}

.form-control {
  margin: 1rem 0;
}

.form-control label {
  display: block;
  font-size: 0.9rem;
}
.form-control input {
  width: 100%;
  height: 40px;
  margin: 5px 0;
  padding: 3px 7px;
  font-size: 1rem;
  font-family: inherit;
}

.form-control-check {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.form-control-check label {
  flex: 1;
}

.form-control-check input {
  flex: 2;
  height: 1rem;
}

@keyframes zoomIn {
  0% {
    scale: 0;
  }
  100% {
    scale: 1;
  }
}

@keyframes zoomOut {
  0% {
    scale: 1;
  }
  100% {
    scale: 0;
  }
}
</style>
