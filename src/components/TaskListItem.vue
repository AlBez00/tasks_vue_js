<template>
<div class="task-list" :id="id">
<div class="task-list__name">{{ name }}</div>
<div class="task-list__date">{{ created }}</div>
<div class="completed" v-if="completed">✓</div>
</div>
</template>

<script>
export default {
  name: 'TaskList',
  props: {
    name: String,
    completed: Boolean,
    id: Number,
    created: Date,
  }
}
</script>

<style lang="scss">
</style>