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
                        <input v-if="punckt.type==='radio'"
                            :type="punckt.type" class="form-check-input"   
               
                            :value="index"
                            v-model="chekButton[0]"
                        >
                        <input v-else
                            :type="punckt.type" class="form-check-input"   
                            
                            :value="index"
                            v-model="chekButton"
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
    props:["punckt", "shablonAnswer"],
    data(){
        return{
            chekButton:[]
        }
    },
    computed: {
       
    },
// необходимо из бавиться от массива  или добавлять set

    methods: {
        changeAnswer(e){
             console.log('11111');     
            this.$emit('changeAnswers', this.chekButton);
           
        }
    }
}
</script>