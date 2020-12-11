<!--
    Name: Angela McLaughlin
    Class Section: CIS-131-W01-Fall 2020
    Date: 12/5/2020
-->

<template>
  <div id="app" class="container">
    <div>
      <Header theTitle="Pop TV Shows!"/>
    </div>
    <div class="cards">
      <Card v-bind:TVList="shows"/>
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Card from './components/Card.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    Header,
    Card
  },
  data(){
    return {
      shows:[],
    }
  },
  mounted(){
    axios.get('https://api.themoviedb.org/3/tv/popular?api_key=28ef03c77cb45d48b1a5a1ce24db79ea')
    .then((res) => {
      this.shows = res.data.results;
      console.log(this.shows)
  })
  }
}
</script>
