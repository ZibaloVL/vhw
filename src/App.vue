<template>
  <div id="app">
   
   
    <app-cart  v-for="(punckt, index) in punckts" :key="index"
      :punckt="punckt"
    >
      
    </app-cart>
   
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

</style>
