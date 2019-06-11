<template>
  <nuxt-link :to="`jokes/${id}`" :event="notFound ? '' : 'click'">
    <div class="joke">
      <p>{{ joke }}</p>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  name: 'joke',
  props: ['joke', 'id'],

  computed: {
    notFound() {
      return this.id === undefined ? true : false;
    }
  }
}
</script>

<style>
  .joke {
    padding: 1rem;
    border: 1px dotted #ccc;
    margin: 1rem 0;
  }
</style>
