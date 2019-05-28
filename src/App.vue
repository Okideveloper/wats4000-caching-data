<template>
  <div id="app">
    <h1>Weather Service</h1>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: rgb(88, 148, 138);
  text-align: center;
  padding-top: 85px;
  font-weight: 500;
  font-size: 18px;
  height: 900px;
  color: #792010;
  width: 85%;
  margin: 50px auto 50px;
}
</style>
