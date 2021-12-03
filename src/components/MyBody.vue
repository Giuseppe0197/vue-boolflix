<template>
  <main>

    <FilmSubComp
    v-for="film, i in filmList" 
    :key="i"
    :details="film"/>

    <SeriesSubComp
    v-for="tv, j in seriesList" 
    :key="j"
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
