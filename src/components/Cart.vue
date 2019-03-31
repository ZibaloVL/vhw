<template>
    <div>  
        <form action=""
            @submit.prevent="changeAnswer($event)"
        >
            <h2>{{punckt.title}}</h2>
            <hr>
            <div class="form-check">
                <div v-for="(answer, index) in punckt.answers" :key="index">  
                    <label class="form-check-label">
                        <input class="form-check-input" 
                            :type="punckt.type"  
                            :value="index"
                            v-model="variantsAnswers"
                        >
                        {{answer}}
                    </label>
                </div>
            </div>
            <hr>
            <button type="submit" class="btn btn-primary btn-sm">send</button>
        </form>
    </div>
</template>

<script>

export default {
    props:{
            punckt:Object,
            
            },
    data(){
        return{
               variantsAnswers:[]
        }
    },
    computed: {
       
    },
// необходимо  добавлять set

    

    methods: {
        
        //событие вспытие ответов формы 
        changeAnswer(e){
            
            this.$emit('changeAnswers', this.variantsAnswers);
           
        }
    }
}
</script>