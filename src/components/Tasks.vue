<template>
  <div :key="task?.id" v-for="task in tasks">
    <TaskVue :task="task" @delete-task="$emit('delete-task', task.id)" />
  </div>
</template>

<script>
import TaskVue from "./Task.vue";
export default {
  name: "TasksItem",
  props: {
    tasks: Array,
  },
  components: {
    TaskVue,
  },
  methods: {
    onClick() {
      console.log("clicked item");
    },
  },
};
</script>
