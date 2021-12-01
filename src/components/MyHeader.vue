<template>
  <header>
      <h1>Boolflix</h1>

      <div id="form">
        <input type="text" placeholder="Cerca un film"  v-model="filmChoice">
        <button @click.prevent="$emit('changeFilm', filmChoice)">Cerca</button>
      </div>
  </header>
</template>

<script>

export default {
  name: 'MyHeader',
  data() {
    return {
      filmChoice: ""
    }
  },
}
</script>

<style lang="scss">
    header {
        height: 80px;
        background-color: black;

        h1 {
            color: red;
            padding-top: 20px;
            float: left;
        }

        #form {
            float: right;
            margin-right: 20px;
            margin-top: 30px;

            input {
                margin-right: 20px;
            }
            button {
                padding: 5px;
                background-color: transparent;
                border: 2px solid white;
                border-radius: 10px;
                color: white;
                cursor: pointer;
            }
        }

    }
</style>
