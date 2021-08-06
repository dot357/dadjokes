<template>
  <div>
    <Searchjokes v-on:search-txt="searchText($event)" />
    <Joke
      v-for="joke in jokes"
      :key="joke.id"
      :id="joke.id"
      :joke="joke.joke"
    />

    
  </div>
</template>

<script>
import axios from "axios";
import Joke from "../../components/Joke.vue";
import Searchjokes from "../../components/Searchjokes.vue";
export default {
  data() {
    return {
      jokes: [],
      checks : {
        isPlayying : false
      }
    };
  },
  components: {
    Joke,
    Searchjokes,
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json",
      },
    };

    try {
      const res = await axios.get("https://icanhazdadjoke.com/search", config);
      console.log(res.data);
      this.jokes = res.data.results;
    } catch (err) {
      console.log(err);
    }
  },
  methods: {
    async searchText(text) {
      console.log(text);

      const config = {
        headers: {
          Accept: "application/json",
        },
      };

      try {
        const res = await axios.get(
          `https://icanhazdadjoke.com/search?term=${text}`,
          config
        );
        console.log(res.data);
        this.jokes = res.data.results;
      } catch (err) {
        console.log(err);
      }
    },
  },
  head() {
    return {
      title: "#CORNY DAD Jokes",
      meta: [
        {
          hid: "desc",
          name: "desc",
          content: "Best corny jokes",
        },
      ],
    };
  },
};
</script>