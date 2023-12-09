<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <div class="tasks-lists">
      <TaskListItem 
      v-for="item in lists"
      :id="item.id"
      :name="item.name"
      :completed="item.completed"
      :created="item.created"

      >
      </TaskListItem>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import TaskListItem from '@/components/TaskListItem.vue'

export default {
  name: 'HomeView',
  components: {
    TaskListItem
  },
  props: {

  },
  data: function () {
    return {
      lists: [
        {
          id: 1,
          name: 'Тестовый список задач',
          completed: false,
          created: new Date(2023, 0, 1, 0, 0, 0)
        },
        {
          id: 2,
          name: 'Тестовый список задач',
          completed: true,
          created: new Date(2023, 0, 3, 0, 0, 0)
        },
      ]
    };
  }
}
</script>
