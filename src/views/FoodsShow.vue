<template>
  <div class="foods-show">
    <h1>{{ food.name }}</h1>
    <img v-bind:src="food.image_url">

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

<span class="heading">Item's Rating</span>
<span class="fa fa-star" v-bind:class="{checked: food.stars >= 1}"></span>
<span class="fa fa-star" v-bind:class="{checked: food.stars >= 2}"></span>
<span class="fa fa-star" v-bind:class="{checked: food.stars >= 3}"></span>
<span class="fa fa-star" v-bind:class="{checked: food.stars >= 4}"></span>
<span class="fa fa-star" v-bind:class="{checked: food.stars >= 5}"></span>
<hr style="border:3px solid #f1f1f1">

<div class="row">
  <div class="side">
    <div>Energy</div>
  </div>
  <div class="middle">
    <div class="bar-container">
      <div class="bar-5"></div>
      <div></div>
    </div>
  </div>
  <div class="side right">
    <div>{{food.energy}}</div>
  </div>
  <div class="side">
    <div>Fat</div>
  </div>
  <div class="middle">
    <div class="bar-container">
      <div class="bar-4"></div>
    </div>
  </div>
  <div class="side right">
    <div>{{food.fat}}</div>
  </div>
  <div class="side">
    <div>Saturated Fat</div>
  </div>
  <div class="middle">
    <div class="bar-container">
      <div class="bar-3"></div>
    </div>
  </div>
  <div class="side right">
    <div>{{food.saturated_fat}}</div>
  </div>
  <div class="side">
    <div>Sugar</div>
  </div>
  <div class="middle">
    <div class="bar-container">
      <div class="bar-2"></div>
    </div>
  </div>
  <div class="side right">
    <div>{{food.sugar}}</div>
  </div>
  <div class="side">
    <div>Sodium</div>
  </div>
  <div class="middle">
    <div class="bar-container">
      <div class="bar-1"></div>
    </div>
  </div>
  <div class="side right">
    <div>{{food.sodium}}</div>
  </div>
</div>


    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">


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
    <h5>Healthy Alternatives:</h5>

    <ul>
       <li v-for="healthy_option in food.healthy_options"> {{ healthy_option.name }} </li>
    </ul>
    
 <!-- <li v-for="healthy_option in food.healthy_options"> {{ healthy_option.name }} </li>
 <div>
      <router-link v-bind:to="heathy_option">
        <h2>{{ healthy_option.name }}</h2>
      </router-link>
    </div> -->

    <div>
      <router-link v-bind:to=" '/foods/' + food.id + '/edit' ">Make Changes</router-link>

    </div>
  </div>
</template>

<style>
/*.checked {
  color: orange;
}*/
{
  box-sizing: border-box;
}

body {
  font-family: Arial;
  margin: 0 auto; /* Center website */
  max-width: 800px; /* Max width */
  padding: 20px;
}

.heading {
  font-size: 25px;
  margin-right: 25px;
}

.fa {
  font-size: 25px;
}

.checked {
  color: orange;
}

/* Three column layout */
.side {
  float: left;
  width: 15%;
  margin-top: 10px;
}

.middle {
  float: left;
  width: 70%;
  margin-top: 10px;
}

/* Place text to the right */
.right {
  text-align: right;
}

/* Clear floats after the columns */
.row:after {
  content: "";
  display: table;
  clear: both;
}

/* The bar container */
.bar-container {
  width: 100%;
  background-color: #f1f1f1;
  text-align: center;
  color: white;
}

/* Individual bars */
.bar-5 {width: 60%; height: 18px; background-color: #4CAF50;}
.bar-4 {width: 30%; height: 18px; background-color: #2196F3;}
.bar-3 {width: 10%; height: 18px; background-color: #00bcd4;}
.bar-2 {width: 4%; height: 18px; background-color: #ff9800;}
.bar-1 {width: 15%; height: 18px; background-color: #f44336;}

/* Responsive layout - make the columns stack on top of each other instead of next to each other */
@media (max-width: 400px) {
  .side, .middle {
    width: 100%;
  }
  /* Hide the right column on small screens */
  .right {
    display: none;
  }
}
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