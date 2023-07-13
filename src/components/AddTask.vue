<template>
  <form action="" class="add-form">
    <div class="form-control">
      <label for="">Task</label>
      <input type="text" name="text" placeholder="Add Task" />
    </div>

    <div class="form-control">
      <label for="">Day & Time</label>
      <input type="text" name="day" placeholder="Add Day & Time" />
    </div>

    <div class="form-control form-control-check">
      <label for="">Set Reminder</label>
      <input type="checkbox" name="reminder" />
    </div>
  </form>
</template>

<script>
export default {
  name: "AddTask",
};
</script>

<style scoped>
.add-form {
  margin-bottom: 2rem;
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
  margin: 5px;
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
</style>
