<template>
  <div>
    <h2>Hello</h2>
    <autocomplete
      :source="[
        { id: 1, name: 'abc' },
        { id: 2, name: 'def' },
      ]"
    ></autocomplete>

    <autocomplete
      source="https://api.github.com/search/repositories?q="
      results-property="items"
      results-display="full_name"
    ></autocomplete>

    <pie-chart
      :data="[
        ['Blueberry', 44],
        ['Strawberry', 23],
        ['Apples', 23],
      ]"
    ></pie-chart>
    <multiselect v-model="value" :options="options" :multiple="true"></multiselect>
  </div>
</template>

<script>
import Multiselect from "vue-multiselect";
import Vue from "vue";
import Chartkick from "vue-chartkick";
import Chart from "chart.js";
import Autocomplete from "vuejs-auto-complete";

Vue.use(Chartkick.use(Chart));
export default {
  // OR register locally
  components: { Multiselect, Autocomplete },
  data() {
    return {
      value: null,
      options: ["list", "of", "options"],
    };
  },
};
</script>

<!-- New step!
     Add Multiselect CSS. Can be added as a static asset or inside a component. -->
<style src="vue-multiselect/dist/vue-multiselect.min.css"></style>

<style></style>
