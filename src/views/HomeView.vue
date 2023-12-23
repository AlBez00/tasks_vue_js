<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <div class="tasks-lists">
      <TaskListItem v-for="list in lists" :task_list="task_list">
      </TaskListItem>
    </div>
    <div class="add_list">
      <h3>Добавить список</h3>
      <label for="list_name">Имя списка</label>
      <input id="list_name" v-model="task_list_name" placeholder="Список задач">
      <button @click="addTaskList">Добавить</button>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import TaskListItem from '@/components/TaskListItem.vue'
import {instance} from '@/api.js';

export default {
  name: 'HomeView',
  components: {
    TaskListItem
  },
  props: {

  },
  data: function () {
    return {
      lists: [],
      task_list_name: ''
    };
  },
  mounted() {
    instance.get('/tasks/lists/')
    .then(response => (this.lists = response.data))
  },
  methods: {
    addTaskList() {
      if (this.task_list_name !== '') {
        instance.post('/tasks/lists/', {'name': this.task_list_name})
        .then(response => this.lists.push(response.data))
      }
    }
  }
}
</script>
