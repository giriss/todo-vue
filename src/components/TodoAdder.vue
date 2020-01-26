<template>
  <form class="input-group mb-3" @submit.prevent="onAdd">
    <input v-model="title" type="text" class="form-control" placeholder="New todo" />
    <div class="input-group-append">
      <button class="btn btn-primary" type="submit">Add</button>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      title: ''
    };
  },
  methods: {
    onAdd() {
      this.$emit('add', this.title);
      this.title = '';
    }
  }
}
</script>
