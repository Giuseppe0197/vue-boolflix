<template>
  <div class="films">
    
    <div class="imgThumbCont">

      <img v-if="details.poster_path === null" src="https://www.losbagliato.it/wp-content/uploads/2021/07/copertina-netflix-23-giugno-960x960.png" alt="" class="imgThumb">

      <img v-else :src="`https://image.tmdb.org/t/p/w342${details.poster_path}`" class="imgThumb">

      <div class="infoFilm">

      <h3 class="titleFilm">Titolo del Film: {{details.title}}</h3>

      <h3>Titolo originale: {{details.original_title}}</h3>

      <img v-if="details.original_language === 'en'" src="../assets/Flag_of_the_United_Kingdom.png" alt="" class="imgFlag">

      <img v-else-if="details.original_language === 'it'" src="../assets/italian_flag.jpg" alt="" class="imgFlag">
      
      <h3 v-else>La lingua originale non disponibile</h3>

      <!-- <h3>{{details.original_language}}</h3> -->

      <h3>Voto Generale: {{details.vote_average / 2}}</h3>

      <p v-if="details.overview">Trama: {{details.overview}}</p>

      <p v-else>Trama non dipsonibile</p>

    </div>

    </div>

    



      

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

    .imgThumbCont {
      position: relative;
    }

    .imgThumbCont:hover .imgThumb{
      display: none;
    }

    .imgThumb{
      width: 100%;
      height: 500px;
    }

    /* .imgThumb:hover {
      display: none;
    } */

    .infoFilm {
      display: none;
      position: absolute;
      top: 5px;
      left: 5px;
    }

    .imgThumbCont:hover .infoFilm {
      display: block;
    }

    span {
      font-weight: bold;
      font-size: 18px;
    }

    .imgFlag {
        width: 20px;
        margin-top: 15px;
    }

    h3 {
        margin-top: 15px;
    }

    p {
      font-size: 13px;
      font-weight: bold;
    }
}

</style>
