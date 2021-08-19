<template>
  <div v-for="(joke, i) in jokesArr">
    <li class="list-item" style="{background-color: red}">
      <span class="bold">{{ joke }}</span>
      <Button class="danger" text="💙" @click="like(i)" />
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
  methods: {
    like(i) {
      console.log(i, "liked");
    },
  },
};
</script>
