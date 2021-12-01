<template>
  <header>
      <h1>Boolflix</h1>

      <div id="form">
        <input type="text" placeholder="Cerca un film">
        <button>Cerca</button>
      </div>

      
  </header>
</template>

<script>
/* import HelloWorld from './components/HelloWorld.vue' */

export default {
  name: 'MyHeader',
  components: {
    
  }
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
