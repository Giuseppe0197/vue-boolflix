<template>
  <div id="app">
    <MyHeader @changeFilm="startSearch" />

    <MyBody :filmList="filmList" />
  </div>
</template>

<script>
import axios from "axios";
import MyHeader from './components/MyHeader.vue'
import MyBody from './components/MyBody.vue'

export default {
  name: 'App',
  components: {
    MyHeader,
    MyBody
  },
  data(){
    return {
      filmList: [],
      filmSearch: "",
      apiUrl: `https://api.themoviedb.org/3/search/movie?api_key=8531cd4b5660045d3ad85863d06b1d4b&language=en-US&query=`,
    }
  },
  methods: {
    getFilmBool() {
      axios
      .get(this.apiUrl+this.filmSearch)
      .then((result) => {
        console.log(result);
        this.filmList = result.data.results
      });
    },
    startSearch(filmSearch){
      this.filmSearch = filmSearch;
      this.getFilmBool();
    }
  },

}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  
}
</style>
