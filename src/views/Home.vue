<script>
import axios from "axios";
export default {
  data: function () {
    return {
      message: "booohoohoohoo!",
      places: [],
      newPlacesParams: {},
      currentPlace: {},
      editCurrentPlace: {},
    };
  },
  created: function () {
    this.indexPlaces();
  },
  methods: {
    indexPlaces: function () {
      console.log("Mic Check CHeck CHeck");
      axios.get("/places").then((response) => {
        console.log(response.data);
        this.places = response.data;
      });
    },
  },
};
</script>

<template>
  <div class="home">
    <h1>All Places</h1>
    <table v-for="place in places" v-bind:key="place.id">
      <h2>Name: {{ place.name }}</h2>
    </table>
    <div></div>
  </div>
</template>

<style>
img {
  width: 250px;
}
</style>


