<template>
  <div v-for="(joke, i) in jokesArr">
    <li class="list-item">
      <span class="bold"> {{ joke }}</span>
      <Button class="btn danger" text="Like 💙" />
    </li>
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
  setup() {
    const jokesArr = ref([]);

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
};
</script>
