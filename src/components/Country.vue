<template>
  <div>
    <h2 v-on:click="countryInfo(country)">{{ country.name }}</h2>
    <div v-if="countryInfoClicked === country">
      <li>Capital: {{ country.capital }}</li>
      <li>Population: {{ country.population }}</li>
    </div>
    <div>

    </div>
    <!-- <country-info></country-info> -->
  </div>
</template>

<script>
import CountryInfo from "./CountryInfo.vue";

export default {
  name: "list-item",
  props: ["country"],
  methods: {
    countryInfo: function (country) {
      this.countryInfoClicked = country;
      console.log(country)
    },
  },
  data() {
    return {
      countryInfoClicked: null,
    };
  },

  components: {
    "country-info": CountryInfo,
  },
};
</script>

<style scoped>
li {
  list-style: none;
}
</style>