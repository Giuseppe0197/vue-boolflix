<template>
  <div id="app">
    <MyHeader :films="filmList" @changeFilm="startSearch"/>

    <MyBody :searchVar="filmSearch" @filmReady="getFilmList"/>
  </div>
</template>

<script>
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

      filmSearch: ""
    }
  },

  methods: {
    getFilmList(allFilm){
      this.filmList = allFilm
    },

    startSearch(filmSearch){
      this.filmSearch = filmSearch
    }
  }
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
