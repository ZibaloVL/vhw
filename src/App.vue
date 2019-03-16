<template>
  <div>
    <div v-if = "index < punckts.length">
      <app-etap
        :etap = "punckts[index]"      
      >
      </app-etap>
      
       <button class="btn btn-primary"
         @click="index++">SEND</button>
    </div>
    <div v-else > 
      <h1>end</h1>
    </div>   
  </div>
</template>

<script>

import AppEtap from './components/Etap.vue';

export default {
    components:{
      AppEtap
    },
    created(){
      
      for(let i = 0; i < this.punckts.length; i++) {
        this.d.push([]);
        for (let n = 0; n <this.punckts[i].answers.length; n++) {
          this.d[i][n]=false;
          
        } 
      }
      console.log (this.d);
    },
    data(){
    return {
      index: 0,//number etap now
      d:[],
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
