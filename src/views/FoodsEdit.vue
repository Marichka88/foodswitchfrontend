<template>
  <div class="foods-edit">

    <div class="row pb30">
        <div class="col-lg-4 col-md-6 mr-auto ml-auto col-sm-8">
            <h3 class="text-white text-center mb30">Edit Food</h3>
            <ul>
              <li v-for="error in errors">{{ error }}</li>
            </ul>
            <form v-on:submit.prevent="submit()">
                <div class="form-group">
                  <input type="text" class="form-control" v-model="food.name" placeholder="Name">
                </div>
                <div class="form-group">
                  <input type="integer" class="form-control" v-model="food.energy" placeholder="Energy">
                </div>

                <div class="form-group">
                  <input type="integer" class="form-control" v-model="food.fat" placeholder="Fat">
                </div>

                <div class="form-group">
                  <input type="integer" class="form-control" v-model="food.saturated_fat" placeholder="Saturated Fat">
                </div>
                <div class="form-group">
                  <input type="integer" class="form-control" v-model="food.sugar" placeholder="Sugar">
                </div>
                <div class="form-group">
                  <input type="integer" class="form-control" v-model="food.sodium" placeholder="Sodium">
                </div>
                 <div class="form-group">
                  <!-- <input type="text" class="form-control" v-model="food.default_filter" placeholder="Default Filter"> -->
                </div>
                <div class="form-group">
                            <!-- <label for="exampleSelect1">Choose Your Filter</label> -->
                            <select class="form-control" id="exampleSelect1">
                                <option>Please Choose the Filter</option>
                                <option>SaltSwitch</option>
                                <option>SugarSwitch</option>
                                <option>FatSwitch</option>
                                <option>EnergySwitch</option>
                                <option>GlutenSwitch</option>
                            </select>

                  </div>





                  <div class="form-group">
                    <button type="submit" class="btn btn-rounded btn-primary btn-block">Update</button>
                </div>
                <hr>
            </form>
        </div>
    </div>

  </div>
</template>

<style>
</style>

<script>
var axios = require("axios");
export default {
  data: function() {
    return {
      errors: [],
      food: {}
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
    submit: function() {
      var clientParams = this.food;
      axios
        .patch("/api/foods/" + this.$route.params.id, clientParams)
        .then(response => {
          this.$router.push("/foods/" + response.data.id);
        })
        .catch(error => {
          this.errors = error.response.data.errors;
        });
    }
  }
};
</script>