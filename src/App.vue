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
  created(){
    for(let i = 0; i < this.punckts.length; i++){
      if(this.punckts[i].type === 'radio'){this.shablonAnswers[i] = false;}
        else if (this.punckts[i].type === 'checkbox'){
          this.shablonAnswers[i] = [];
           for(let n=0; n < this.punckts[i].answers.length; n++){
           this.shablonAnswers[i].push(false);}
      }
    console.log("shablonAnswers  " + this.shablonAnswers);  
    }
  }
  
}
</script>

<style>

</style>
