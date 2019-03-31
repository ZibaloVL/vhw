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
    props:{
        punckts:Array, 
        shablonAnswers:Array
        },
    data(){
        return{
            
        }
    },
    computed: {
      
    },
    methods: {
        anser(index){
            if(this.shablonAnswers.length === this.punckts.length){ 
                let ans = [];
                let answers = this.punckts[index].answers;
                let nomerAnswer = this.shablonAnswers[index];
                if (this.punckts[index].type === 'radio'){
                    return answers[nomerAnswer];
                    }
                else if (this.punckts[index].type === 'checkbox'){    
                    nomerAnswer.forEach(function(num, i, nomerAnswer){ans.push(answers[num])})
                    return ans.join(', ');
                }
            }     
       }
    }
}
</script>