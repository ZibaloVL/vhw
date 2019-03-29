<template>
  <div id="app">
   
   
    <app-cart  v-for="(punckt, index) in punckts" :key="index"
      :punckt="punckt"
      :shablonAnswer="shablonAnswers[index]"
      @changeAnswers="getAnswers($event, index)" 
    >
      
    </app-cart>
   
  </div>
</template>

<script>

import AppCart from './components/Cart'
import AppTable from './components/Tableanswer'

export default {
  name: 'app',
  components: {
      AppCart,
      AppTable
  },
  data () {
    return {
      shablonAnswers:[],//шаблон ответов экзаменуемого
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
  },
  methods: {
    getAnswers(chekButton, index){
        this.shablonAnswers.push(chekButton);
    }
  }
  
}
</script>

<style>

</style>
