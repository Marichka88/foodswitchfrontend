<template>
  <div class="foods-show">
    <h1>{{ food.name }}</h1>
    <h5>Energy: {{ food.energy }}</h5>
    <h5>Fat: {{ food.fat }}</h5>
    <h5>Saturated Fat: {{ food.saturated_fat }}</h5>
    <h5>Sugar: {{ food.sugar }}</h5>
    <h5>Sodium: {{ food.sodium }}</h5>
    <h5>Default Filter: {{ food.default_filter }}</h5>
    <h5>Diets:</h5>
    <ul>
      <li v-for="diet_name in food.diet_names"> {{ diet_name }} </li>
    </ul>
    <h5>Suggestions:</h5>
    <ul>
       <li v-for="healthy_option in food.healthy_options"> {{ healthy_option.name }} </li>
    </ul>



    <div>
      <router-link v-bind:to=" '/foods/' + food.id + '/edit' ">Edit</router-link>
    </div>
  </div>
</template>

<style>
</style>

<script>
var axios = require('axios');
export default {
  data: function() {
    return {
      food: {
        id: "",
        name: "",
        energy: "",
        fat: "",
        saturated_fat: "",
        sugar: "",
        sodium: "",
        default_filter: "",
        diets: []
      }
    };
  },
  created: function() {
    axios
      .get("/api/foods/" + this.$route.params.id)
      .then(response => {
        this.food = response.data;
      });
  },
  methods: {
    destroyFood: function() {
      axios
        .delete("/api/foods/" + this.food.id)
        .then(response => {
          this.$router.push("/");
        });
    }
  }
};
</script>