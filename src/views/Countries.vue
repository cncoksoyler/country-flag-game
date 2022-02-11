<template>
  <app-layout title="Dispatch">
    <template #header>
      <h2 class="font-semibold text-xl text-gray-800 leading-tight">
        Dispatch
      </h2>
    </template>

    <div class="py-12">
      <div v-for="country in countries" :key="country.name">
        <!-- {{ country.name.common }} -->
        <div class="flex flex-row inline-block justify-center">
          <div class="flex flex-col col-span-6 inline-block justify-center m-5">
            <img :src="country.flags.png" :alt="country.name.common" />
          </div>
          <div
            class="flex flex-col col-span-6 inline-block justify-center ml-5"
          >
            <input type="text" v-model="dummy.country" />
          </div>
        </div>
      </div>
    </div>
  </app-layout>
</template>
 <script>
import { defineComponent } from "vue";

export default {
  data() {
    return {
      countries: [],
      dummy: [""],
    };
  },
  components: {
    AppLayout,
  },
  beforeMount() {
    fetch("https://restcountries.com/v3.1/subregion/europe")
      .then((response) => response.json())
      .then((data) => (this.countries = data));
  },
};
</script>