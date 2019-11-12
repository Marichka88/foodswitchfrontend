<template>
  <div class="foods-index">

    <h1>
      <p class="text-custom-1 text-center p-4">Please Make Your Food Choice or Use a Search Box</p>
    </h1>

    <form class="d-flex justify-content-center form-inline mb-4" v-on:submit.prevent="search()">
        <label class="sr-only" for="inlineFormInput">Search</label>
        <input type="text" class="form-control mb-3 mr-sm-2 mb-sm-0" id="inlineFormInput" v-model="searchTerm" placeholder="Search by Name">
        <button type="submit" class="btn btn-success">Search</button>
    </form>


    <div class="row">
      <div class="col-lg-6" v-for="food in foods">
        <div class="card mb-3">
          <router-link v-bind:to="'/foods/' + food.id">
            <div class="row no-gutters">
              <div class="col-md-4">
                <img v-bind:src="food.image_url" class="card-img" alt="...">
              </div>
              <div class="col-md-8">
                <div class="card-body">
                  <h5 class="card-title">{{ food.name }}</h5>
                  <p class="card-text">Stars: {{ food.stars }}</p>
                </div>
              </div>
            </div>
          </router-link>
        </div>
      </div>
    </div>
    <div class="video-container">
      <div class="d-flex justify-content-center">
        <iframe width="500" height="300" src="https://www.youtube.com/embed/VUyEPf-IvdM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
      </div>
    </div>
  </div>
</template>

<style>\
.video-container {
  margin: 30px 0px;
  background-color: white;
}

.text-custom-1 {
  color: dimgray;
}

.card {
  background-color: lightgray;
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