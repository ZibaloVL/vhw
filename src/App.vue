<template>
  <div id="app">
   
   
    <app-cart  
      v-show="numCart === index"
      v-for="(punckt, index) in punckts" :key="index"
      :punckt="punckt"
      @changeAnswers="getAnswers($event, index)" 
    >
    </app-cart>
    <app-table v-show="numCart === punckts.length"
      :punckts="punckts"
      :shablonAnswers="shablonAnswers"
    >
    </app-table>
   
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
      numCart:0,//номер карточки вопросов необходима для показа страницы
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
    
    getAnswers(variantsAnswers, index){

        this.$set( this.shablonAnswers, index,  variantsAnswers)
        this.numCart++;
        
    }
    
  }
  
}
</script>

<style>

</style>
