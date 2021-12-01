<template>
  <div class="films">

      <!-- <img :src="details.poster_path"> -->

      <h3 class="titleFilm">{{details.title}}</h3>

      <h3>{{details.original_title}}</h3>

      <h3>{{details.original_language}}</h3>

      <h3>{{details.vote_average}}</h3>

      

  </div>
</template>

<script>


export default {
  name: 'FilmSubComp',
  props: {
    details: Object
  }
}
</script>

<style lang="scss">

</style>
