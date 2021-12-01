<template>
  <main>

  </main>
</template>

<script>


export default {
  name: 'MyBody',
  data() {
      return {
          serchVar: "",
          apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=8531cd4b5660045d3ad85863d06b1d4b&language=en-US&query=" + this.serchVar + "&page=1&include_adult=false"
      }
  },

}
</script>

<style lang="scss">

main {
    height: calc(100vh - 80px);
    background-color: red;
}

</style>
