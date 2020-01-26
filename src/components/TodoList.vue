<template>
  <ul class="list-group">
    <Todo
      v-for="item in items"
      :key="item.title"
      :title="item.title"
      :completed="item.completed"
      @toggle="toggle(item.title)"
      @delete="$emit('delete', item.title)"
    />
  </ul>
</template>

<script>
import Todo from './Todo.vue';

export default {
  props: ['items'],
  components: { Todo },
  methods: {
    toggle(title) {
      this.$emit('toggle', title);
    }
  }
}
</script>
