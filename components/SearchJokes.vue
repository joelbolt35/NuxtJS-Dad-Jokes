<template>
  <form v-on:submit.prevent="onSubmit">
    <input class="form-control" type="text" v-model="text" placeholder="Search Jokes...">
    <input class="form-control" type="submit" value="Search Jokes">
  </form>
</template>

<script>
export default {
  name: 'SearchJokes',
  data() {
    return {
      text: ''
    }
  },

  methods: {
    onSubmit() {
      this.$emit('search-text', this.text);
      this.text = '';
    }
  }
}
</script>

<style>

</style>
