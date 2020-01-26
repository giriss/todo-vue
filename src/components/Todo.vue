<template>
  <li
    class="list-group-item list-group-item-action"
    :class="{ 'completed': completed }"
    @click="toggle"
  >
    {{ title }}
    <span class="float-right" @click.stop="$emit('delete')">
      <i class="fas fa-times"></i>
    </span>
  </li>
</template>

<script>
export default {
  props: ['title', 'completed'],
  methods: {
    toggle() {
      this.$emit('toggle');
    }
  }
}
</script>

<style scoped>
.completed {
  text-decoration: line-through;
}
</style>
