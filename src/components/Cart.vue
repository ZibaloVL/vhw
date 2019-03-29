<template>
    <div>  
        <form action="">
            <h2>{{punckt.title}}</h2>
            <hr>
            <div class="form-check">
                <div v-for="(answer, index) in punckt.answers" :key="index">  
                    <label class="form-check-label">
                        <input v-if="punckt.type==='radio'"
                            :type="punckt.type" class="form-check-input"   
                            @change="changeAnswer($event, index)"
                            :value="index"
                            v-model="chekButton[0]"
                        >
                        <input v-else
                            :type="punckt.type" class="form-check-input"   
                            @change="changeAnswer($event, index)"
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
       typeQuestion() {
             (this.punckt.type === 'radio') ?  this.radioButton : this.chekButton ;  
             
        },



    },
 // организация проброса значений для вывода элементов: проброс массива и его перебор
// 

    methods: {
        changeAnswer(e, numAnswer){
             console.log('11111');
             this.metka =!this.metka;
            
            this.$emit('changeAnswers', numAnswer);
           
        }
    }
}
</script>