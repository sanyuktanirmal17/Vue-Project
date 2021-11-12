<template>
  <div id="app">
    <Header /> 

<b-container class="bv-example-row">
  <b-row>
    <b-col sm ="6" offset= "3"></b-col>
     <Box />
  </b-row>
</b-container>
</div>
</template>

<script>
import Header from './components/Header.vue'
import Box from './components/Box.vue'

export default {
  name: 'App',
  components: {
    Header,
    Box
  },

data () {
  return {
    results: []
  }
},
  mounted: function()
{
  fetch('http://localhost:3000/sampletable', 
  {
    method: 'get'
  })
  .then((response) => {
     console.log(response.json())
    return response.json()
  })
  .then((jsonData) => {
    this.results = jsonData.results
  })
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
