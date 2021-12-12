<template>
  <div>
    <input
      type="text"
      v-model="filter"
      @keydown="onkeydown"
      class="country-choise"
    />
    <br />
    <country-select
      v-if="filter.length > 1"
      :countryList="filterCountries"
    ></country-select>
    <br />
  </div>
</template>

<script>
import CountrySelect from "./CountrySelect.vue";

export default {
  name: "Countries",
  components: {
    CountrySelect,
  },
  data() {
    return {
      countries: [],
      filterCountries: [],
      filter: "",
    };
  },

  beforeCreate: async function () {
    await fetch(`http://localhost:3001`)
      .then((result) => {
        return result.json();
      })
      .then((res) => {
        this.countries = res;
      });
  },
  methods: {
    onkeydown() {
      this.filterCountries = this.countries.filter((country) =>
        country.name.includes(this.filter)
      );
    },
  },
};
</script>

//
<style>
.country-choise {
  width: 350px;
  height: 35px;
  border: 0;
  background-color: rgb(201, 195, 195);
  border-bottom: 3px solid gray;
  font-size: 24px;
}
</style>
