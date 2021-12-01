<template>
  <div class="films">

      <!-- <img :src="`https://image.tmdb.org/t/p/w342details.backdrop_path`"> -->

      <h3 class="titleFilm">Titolo del Film: {{details.title}}</h3>

      <h3>Titolo originale: {{details.original_title}}</h3>

      <img v-if="details.original_language === 'en'" src="../assets/Flag_of_the_United_Kingdom.png" alt="">
      
      <h3 v-else>La lingua originale non disponibile in inglese</h3>

      <h3>Voto Generale: {{details.vote_average}} / 10</h3>

      

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

.films {
    margin-left: 30px;
    width: calc(100% / 4 - 10px);
    margin: 10px 5px;
    border: 3px solid black;
    color: red;

    img {
        width: 20px;
        margin-top: 15px;
    }

    h3 {
        margin-top: 15px;
    }
}

</style>
