<template>
  <select class="country-select">
    <option
      v-for="country in countryList"
      v-bind:key="country.name"
      value="country.name"
    >
      {{ country.name }}
    </option>
  </select>
</template>

<script>
export default {
  props: {
    countryList: {
      type: Array,
    },
  },
};
</script>

<style>
.country-select {
  width: 350px;
  height: 35px;
  border: 0;
  border-bottom: 3px solid gray;
  font-size: 16px;
}
</style>
