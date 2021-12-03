<template>
  <div class="series">
    
    <div class="imgThumbCont">

      <img v-if="details.poster_path === null" src="https://www.losbagliato.it/wp-content/uploads/2021/07/copertina-netflix-23-giugno-960x960.png" alt="" class="imgThumb">

      <img v-else :src="`https://image.tmdb.org/t/p/w342${details.poster_path}`" class="imgThumb">

      <div class="infoSeries">

        <h3 class="titleSeries">Titolo della serie: {{details.name}}</h3>

        <h3>Titolo originale: {{details.original_name}}</h3>

        <img v-if="details.original_language === 'en'" src="../assets/Flag_of_the_United_Kingdom.png" alt="" class="imgFlag">

        <img v-else-if="details.original_language === 'it'" src="../assets/italian_flag.jpg" alt="" class="imgFlag">

        <img v-else-if="details.original_language === 'ja'" src="../assets/flag_japan.png" alt="" class="imgFlag">

        <img v-else-if="details.original_language === 'cn'" src="../assets/flag_china.png" alt="" class="imgFlag">
        
        <h3 v-else>La lingua originale non &egrave; disponibile</h3>

        <!-- <h3>{{serie.original_language}}</h3> -->

        <h3>Voto Generale: <star-rating :rating="getStar()" :star-size = "20" :increment = "1" :show-rating="false"/></h3>

        <p v-if="details.overview">Trama: {{details.overview}}</p>

        <p v-else>Trama non dipsonibile</p>

      </div>

    </div>


  </div>
</template>

<script>
import StarRating from 'vue-star-rating'

export default {
  name: 'SeriesSubComp',
  components: {
    StarRating
  },
  props: {
    details: Object
  },
  methods: {
    getStar(){
      return this.details.vote_average / 2
    }
  }
}
</script>

<style lang="scss">
.series {
    margin-left: 30px;
    width: calc(100% / 4 - 10px);
    margin: 10px 5px;
    color: white;
    background-color: black;
}
.imgThumbCont {
  position: relative;
}

.series:hover .imgThumb{
  display: none;
}

.imgThumb{
  width: 100%;
  height: 500px;
}

.infoSeries {
  display: none;
  position: absolute;
  height: 100vh;
  top: 5px;
  left: 5px;
  overflow-y: auto;
}

.series:hover .infoSeries {
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
</style>
