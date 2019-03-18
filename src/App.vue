<template>
  <div id="app">
   <div v-for="(punckt, index) in punckts " :key="index">
     <h2>{{ punckt.title }}</h2>
    
      <div  class = "form-check" style = "text-align: left"
        v-for="(answer, index_answer) in punckt.answers"  :key="index_answer">      
        <input  class = "form-check-input"
            :type="punckt.type" 
           :value="answer"
           v-model="choise_answer[index]"
           >
         <label class="form-check-label">{{answer}}</label>  
      </div>

      <div class="form-check">
        <label  class="form-check-input"
         v-for="(answer, index_answer) in punckt.answers"  :key="index_answer">  
         <input  class = "form-check-input"
            :type="punckt.type" 
            :value="answer"
            v-model="choise_answer[index]"
           >
          {{answer}}
        </label>
      </div>


    
       
     

   </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      choise_answer:[],
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
