<template>
  <div class="about">
    <h1>This is an about page</h1>
    <country-guesser />
  </div>
</template>

<script>
import CountryGuesser from "../components/CountryGuesser.vue";

export default {
  components: {
    CountryGuesser,
  },
};
</script>
