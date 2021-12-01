<template>
  <main>

    <FilmSubComp
    v-for="film, i in filteredFilm" 
    :key="i"
    :details="film"/>

  </main>
</template>

<script>
import axios from "axios";
import FilmSubComp from '@/components/FilmSubComp.vue'


export default {
  name: 'MyBody',
  components: {
    FilmSubComp
  },
  props: {
      searchVar: String
  },
  data() {
      return {
          /* searchVar: "", */
          apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=8531cd4b5660045d3ad85863d06b1d4b&language=en-US&query=" + this.searchVar,
          filmList: [],
          films: []
      }
  },

   created() {
      this.getFilmBool()
  },

  computed: {

      filteredFilm() {
          if (this.searchVar === ""){
              return this.filmList
          } else if (this.searchVar === "all") {
              return this.filmList
          }
            return this.filmList.filter((item) => {
                return item.title.toLowerCase().includes(this.searchVar.toLowerCase())
            })
      }

  },

  methods: {
      getFilmBool() {

        axios
        .get(this.apiUrl)
        .then((result) => {
            
            this.filmList = result.data.reuslts

            this.filmList.forEach(element => {
                if(!this.films.includes(element.title)){
                    this.films.push(element.title)
                }
            });

            this.$emit("filmReady", this.title)

        })
        
      },

      getTitle(titleType) {
          this.searchVar = titleType
      }
  }

}
</script>

<style lang="scss">

main {
    height: calc(100vh - 80px);
    background-color: red;
}

</style>
