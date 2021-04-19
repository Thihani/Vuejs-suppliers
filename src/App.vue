<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1> What do you want? </h1>
    <div class="container">
    <div class="row">
      <div class="col-sm">
        <router-link to="/suppliers">Go to Suppliers list</router-link>
      </div>
      <div class="col-sm">
        <router-link to="/map">Go to Suppliers map</router-link>
      </div>
      <p v-if="loading">Requête en cours</p>
      <p v-if="error !=null" style="color:red">{{error}}</p>
    </div>
</div>
   
    <router-view :suppliers="suppliers"></router-view>
  </div>
</template>

<script>
const axios = require("axios").default;
export default {
  name: 'App',
  components: {
  },
  data(){
    return {
      message: 'User has clicked here!',
      suppliers:[],
      loading: true,
      error: null,
    }
  },
  methods:{
    onSuppliersListClick(){
      alert(this.message)
    },
    onMapClick(){
      alert(this.message)
    }
  },
 created(){
    axios.get('https://api-suppliers.herokuapp.com/api/suppliers')
    .then(response => {
      this.suppliers = response.data;
      this.loading = false})
    .catch(error => this.error = error)
   },
  
}
</script>

<style>
.col-sm{
  background-color: #41b883;
  margin:50px;
  height:50px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
