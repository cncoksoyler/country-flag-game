<template>
  <div class="countries">
    <h1>This is an about page</h1>
    <country-guesser
      v-for="country in countries"
      :key="country.cca2"
      :country="country"
    />
  </div>
</template>

<script>
import CountryGuesser from "../components/CountryGuesser.vue";

export default {
  data() {
    return {
      countries: [],
      dummy: [],
    };
  },
  components: {
    CountryGuesser,
  },
  beforeMount() {
    fetch("https://restcountries.com/v3.1/subregion/europe")
      .then((response) => response.json())
      .then((data) => (this.countries = data));
  },
};
</script>

<style>
img {
  border: solid 1px black;
  border-radius: 3px;
}
input {
  margin-bottom: 5px;
}
</style>