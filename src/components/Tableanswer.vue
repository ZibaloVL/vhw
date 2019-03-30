<template>
    <div>  
        <table class="table">
            <thead>
                <tr>
                    <th>вопрос</th>
                    <th>ответ</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(punckt, index) in punckts" :key="index">
                    <td scope="row">{{ index + 1 }}</td>
                    <td>{{punckt.title}}</td>
                    <td>{{(anser(index))}}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
// join ответов создать

export default {
    props:["punckts", "shablonAnswers"],
    data(){
        return{
            
        }
    },
    computed: {
      
    },
 // разобраться с массивами многомергыми
 // нет свойтсва длины. попробовать задавать через ыуе// сделать обьектом
    methods: {
         anser(index){
            console.log("shablonAnswers____" + this.shablonAnswers[index].length);
             
           /* 
            let ans = '';
            for(let i = 0; i < this.shablonAnswers[index].length; i++){
                let num = this.shablonAnswers[index][i];
                ans = this.punckts[index].answers[num] + '' + ans  ;    
           }*/
          // return ans;
           
       }
    }
}
</script>