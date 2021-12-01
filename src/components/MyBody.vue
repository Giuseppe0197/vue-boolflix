<template>
  <main>

    <FilmSubComp
    v-for="film, i in filmList" 
    :key="i"
    :details="film"/>

  </main>
</template>

<script>
import FilmSubComp from '@/components/FilmSubComp.vue'

export default {
  name: 'MyBody',
  components: {
    FilmSubComp
  },
  props: {
      filmList: Array
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
