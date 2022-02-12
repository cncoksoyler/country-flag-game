<template>
  <div>
    <img
      :src="country.flags.svg"
      style="height: 250px; border: solid 5px black"
    />
    <br />
    <input type="text" v-model="guess" />
    <button type="button" @click="checkGuess">Check</button>
    <hr />
  </div>
</template>

<script>
export default {
  props: ["country"],
  data() {
    return {
      guess: null,
    };
  },
  methods: {
    checkGuess() {
      if (this.guess === this.country.name.common) {
        console.log("Bildiniz");
      } else {
        console.log("Tekrar deneyiniz plz");
      }
    },
  },
};
</script>
