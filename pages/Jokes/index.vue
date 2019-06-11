<template>
  <div>
    <SearchJokes v-on:search-text="searchText"/>
    <Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke"/>
  </div>
</template>

<script>
import Joke from '../../components/Joke'
import SearchJokes from '../../components/SearchJokes'
import axios from 'axios'

export default {
  components: {
    Joke,
    SearchJokes
  },
  data() {
    return {
      jokes: []
    };
  },
  methods: {
    async searchText(text) {
      const config = {
        headers: {
          accept: 'application/json'
        }
      }
      let res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, config);
      
      if(res.data.total_jokes != 0)
        this.jokes = res.data.results;
      else
        this.jokes = [{
          joke: "No jokes here buddy!"
        }];
    }
  },
  async created() {
    const config = {
      headers: {
        accept: 'application/json'
      }
    }

    try {
      const res = await axios.get('https://icanhazdadjoke.com/search', config)
      this.jokes = res.data.results;
    } catch (error) {
      console.log(error);    
    }

  },

  head() {
    return {
      title: "Dad Jokes",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Best place for corny dad jokes"
        }
      ]
    }
  }
};
</script>
  
<style>
</style>
