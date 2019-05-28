<template>
    <ul class="favorite-cities">
        <li><h2>Favorite Cities</h2></li>
        <li v-if="favoriteCities.length < 1">No favorites cities to display.</li>
        <li v-for="(city,index) in favoriteCities" :key="index">
          <router-link v-bind:to="{ name: 'CurrentWeather', params: { cityId: city.id } }">{{ city.name }}</router-link> <button v-on:click="removeCity(city)" class="remove">x</button>
        </li>
    </ul>
</template>

<script>
export default {
  name: 'FavoriteCities',
  data () {
    return {}
  },
  props: {
    favoriteCities: Array
  },
  methods: {
    removeCity: function (city) {
      // This will allow for the removal of the selected city
      // Hint: Use `indexOf(city)` on the `this.favoriteCities` array and then use the `splice()` method
      let cityIndex = this.favoriteCities.indexOf(city)
      this.favoriteCities.splice(cityIndex,1)
      // This will cache favoriteCities. using $ls.set 
      this.$ls.set('favoritecities', this.favoriteCities)
    }
  }
}
</script>

<style scoped>
.favorite-cities {
  list-style-type: none;
  padding: 10px;
  background: #ccc;
  width: 25%;
  float: right;
}
.remove {
  font-size: 0.8rem;
  color: white;
  background: #AA0000;
  padding: 2px;
  cursor: pointer;
}
</style>