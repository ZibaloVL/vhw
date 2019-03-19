<template>
  <div id="app">
   
   <div v-if = "numCart  < punckts.length">
    <app-cart>
      
    </app-cart>
   </div>
  </div>
</template>

<script>

import AppCart from './components/Cart'

export default {
  name: 'app',
  components: {
      AppCart
  },
  data () {
    return {
      numCart:0,//номер карточки вопросов
      punckts: [
                {
                  type: 'radio',
                  title: 'Какой тег задаёт ссылку?',
                  answers: [
                    'a',
                    'div',
                    'span',
                    'img'
                  ]
                },

                {
                  type: 'checkbox',
                  title: 'Какие из  этих тегов строчные?',
                  answers: [
                    'a',
                    'div',
                    'span',
                    'img'
                  ]
                }
              ]
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
