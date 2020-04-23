<template>
  <form id="app" @submit.prevent="createTask">
    <label for="tast" class="label">tarea: </label>
    <input type="text" v-model="newTask" id="id" />
    <input type="submit" value="Crear tarea" />
    <ul>
      <li
        v-for="(task, i) in tasks"
        :key="'task' + i"
        :class="{ completed: task.completed }"
        @click="completedTask(task.text)"
      >
        {{ task.text }}
      </li>
    </ul>
  </form>
</template>
<script>
export default {
  data: () => ({
    newTask: "",
    tasks: [],
  }),
  methods: {
    createTask() {
      let task = {
        text: this.newTask,
        completed: false,
      };
      this.tasks.push(task);
      this.newTask = "";
      console.log(this.tasks);
    },
    completedTask(taskText){
        for(let i = 0; i < this.tasks.length; i++){
            let task = this.tasks[i];
            if(taskText === task.text) {
                task.completed = !task.completed
            }
        }
    }
  },
};
</script>

<style scoped>
.completed {
  text-decoration: line-through;
  color: grey;
}
</style>
