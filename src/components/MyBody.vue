<template>
  <main>

    <FilmSubComp
    v-for="film in filmList" 
    :key="film.id"
    :details="film"/>

    <SeriesSubComp
    v-for="tv in seriesList" 
    :key="tv.id"
    :details="tv"/>

  </main>
</template>

<script>
import FilmSubComp from '@/components/FilmSubComp.vue'
import SeriesSubComp from '@/components/SeriesSubComp.vue'


export default {
  name: 'MyBody',
  components: {
    FilmSubComp,
    SeriesSubComp,
  },
  props: {
      filmList: Array,
      seriesList: Array
  },
}
</script>

<style lang="scss">

main {
    height: calc(100vh - 80px);
    background-color: #434343;
    overflow-y: scroll;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
}

</style>
