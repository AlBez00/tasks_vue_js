<template>
<div class="task-list" :id="id">
<div class="task-list__number">{{ task_list.id }}</div>
<div class="task-list__name">{{ task_list.name }}</div>
<div class="task-list__date">{{ task_list.created }}</div>
<div class="completed" v-if="task_list.completed">✓</div>
<div class="completed" v-else>x</div>
</div>
</template>

<script>
export default {
  name: 'TaskList',
  props: {
    task_list: Object
  }
}
</script>

<style lang="scss">
</style>