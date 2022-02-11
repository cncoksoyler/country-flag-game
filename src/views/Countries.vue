<template>
  <div class="countries">
    <h1>This is an about page</h1>

    <div v-for="country in countries" :key="country.name">
      <hr />

      <div class="flex flex-col col-span-6 inline-block justify-center m-5">
        <img :src="country.flags.png" :alt="country.name.common" />
      </div>
      <br />
      
      <div class="flex flex-col col-span-6 inline-block justify-center ml-5">
        <input type="text" v-model="dummy"/>
     
      </div>
    </div>
  </div>
</template>
 <script>
export default {
  data() {
    return {
      countries: [],
      dummy: [],         
    };
  },
  components: {},
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