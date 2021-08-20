<template>
  <div>
    <input
      v-model="search"
      class="inputValue"
      type="text"
      placeholder="Search by words..."
    />
    <div v-for="(joke, i) in searchHandler">
      <li class="list-item">
        <span class="bold">{{ joke }}</span>
        <Button class="danger" text="💙" @click="like(joke, i, $event)" />
      </li>
    </div>
  </div>
</template>

<script>
import Button from "./Button";
import { ref } from "vue";

export default {
  name: "Jokes",
  props: {
    jokesArr: Array,
  },
  components: {
    Button,
  },
  data() {
    return { likedJokes: [], search: "" };
  },
  setup() {
    // An empty array for filling
    const jokesArr = ref([]);

    // Getting jokes API
    (async function() {
      try {
        const getJokes = await fetch(
          "https://v2.jokeapi.dev/joke/Any?type=single&amount=10"
        );
        const resJokes = await getJokes.json();
        const jokesData = await resJokes.jokes;
        jokesData.forEach((text) => jokesArr.value.push(text.joke));
      } catch (err) {
        console.error(err.message);
      }
    })();
    return { jokesArr };
  },
  methods: {
    like(joke, i, e) {
      // Like a joke
      e.target.closest(".list-item").classList.toggle("liked");

      // Adding liked jokes in array
      this.likedJokes.push(joke);

      // Saving in local storage
      localStorage.setItem("likedJokes", JSON.stringify(this.likedJokes));
    },
  },
  computed: {
    searchHandler() {
      return this.jokesArr.filter((joke) => {
        return joke.toLowerCase().match(this.search.toLowerCase());
      });
    },
  },
};
</script>
