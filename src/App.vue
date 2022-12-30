<template>
  <div class="container">
    <HeaderItemVue title="Task Tracker" />
    <Tasks :tasks="tasks" @delete-task="deleteTask" />
  </div>
</template>

<script>
import HeaderItemVue from "./components/HeaderItem.vue";
import Tasks from "./components/Tasks.vue";
export default {
  name: "App",
  components: {
    HeaderItemVue,
    Tasks,
  },
  data() {
    return {
      tasks: [],
    };
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: "Doctor's Appointment",
        day: "1st March at 2:30pm",
        reminder: true,
      },
      {
        id: 2,
        text: "Standup Meeting",
        day: "1st March at 3:30pm",
        reminder: true,
      },
      {
        id: 3,
        text: "Coding Time",
        day: "1st March at 1:30pm",
        reminder: false,
      },
    ];
  },
  methods: {
    deleteTask(id) {
      this.tasks = this.tasks.filter((task) => task.id !== id);
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap");
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: "Poppins", sans-serif;
}
.container {
  max-width: 800px;
  margin: 30px auto;
  overflow: auto;
  min-height: 500px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
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
