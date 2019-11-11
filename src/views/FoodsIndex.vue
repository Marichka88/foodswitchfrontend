<template>
  <div class="foods-index">
    <h1>
      <p class="text-success">Please Make Your Food Choice or Use a Search Box</p>
    </h1>

    <form v-on:submit.prevent="search()">
      <input type="text" v-model="searchTerm" placeholder="Search by Name">
      <input type="submit" value="Search">
    </form>

    <iframe width="560" height="315" src="https://www.youtube.com/embed/VUyEPf-IvdM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

    <div v-for="food in foods">
      <router-link v-bind:to="'/foods/' + food.id">
        <h2>{{ food.name }}</h2>
      </router-link>
    </div>
  </div>
</template>

<style>
img {
  width: 250px;
}
</style>

<script>
var axios = require('axios');
export default {
  data: function() {
    return {
      foods: [],
      searchTerm: ""
    };
  },
  created: function() {
    axios
      .get("/api/foods")
      .then(response => {
        this.foods = response.data;
      });
  },
  methods: {
    search: function() {
      axios
        .get("/api/foods?search=" + this.searchTerm)
        .then(response => {
          this.foods = response.data;
        });
    }
  }
};
</script>