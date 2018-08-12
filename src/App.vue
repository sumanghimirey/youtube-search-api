<template>
  <div id="app">

  <SearchBar @termsChange="searchInput"> </SearchBar>
  <VideoList :videos="videos"> </VideoList>

  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar';
import VideoList from './components/VideoList';
const API_KEY = 'AIzaSyAJaXKUVHjksiGniRkbmex7uzDLdF0eFlM';
export default {
  name: 'App',
  components:{
    SearchBar,
    VideoList
  },
  data(){
     return {
      videos:[]
    }
  },
  methods: {
    searchInput(searchTerms) {
    axios.get('https://www.googleapis.com/youtube/v3/search',{
      params:{
        key:API_KEY,
        type:'video',
        part:'snippet',
        q:searchTerms

      }
    }).then(response => {
   
      this.videos = response.data.items
      console.log(this.videos)
     
    })
      
    }
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
