<template>
  <div id="app">
   
   <div v-if = "numCarts  < punckts.length">
    <app-cart
      :title = punckts[numCarts].title
      :answers = punckts[numCarts].answers
      :typeInput = punckts[numCarts].type
      :num = numCarts
      :cartAnswer = cartAnswers[numCarts]
    >      
    </app-cart>
    </div>
    <div v-else>TABLE</div>
    <button class = "btn btn-primary"
      @click="numCarts++"
    >ДАЛЬШЕ</button>
   
  </div>
</template>

<script>

import AppCart from './components/Cart'

export default {
  name: 'app',
  components: {
      AppCart
  },
  created() {
    for(let i = 0; i <this.punckts.length; i++){
      if (this.punckts[i].type === 'radio'){this.cartAnswers.push('');}
        else{this.cartAnswers.push(Array());}
        console.log(this.cartAnswers);
    }
  },
  data () {
    return {
      numCarts: 0, //номер карточки вопросов
      cartAnswers:[], //карта ответов
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
