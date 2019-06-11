<template>
  <header class="header">
    <h1 class="title">Dad Jokes</h1>
    <div class="btn-group" role="group" aria-label="Basic example">
      <nuxt-link to="/" type="button" class="btn btn-secondary">Home</nuxt-link>
      <nuxt-link to="/jokes" type="button" class="btn btn-secondary">Jokes</nuxt-link>
      <nuxt-link to="/about" type="button" class="btn btn-secondary">Home</nuxt-link>
    </div>
  </header>
</template>

<script>
export default {
  name: 'AppHeader'
};
</script>

<style>
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 1rem;
    padding-bottom: 1rem;
    border-bottom: 1px dotted #ccc;
  }

  .header .title {
    font-size: 3rem;
    color: #526488;
  }


  .header a {
    background: #333;
    padding: 0.3rem 1rem;
    margin-right: 0.5rem;
  }

</style>
