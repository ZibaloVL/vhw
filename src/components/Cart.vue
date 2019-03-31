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
                        <input 
                            :type="punckt.type" class="form-check-input"   
                            @change="onChange($event, index)"
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
    props:{punckt:Object,
            shablonAnswer:Object},
    data(){
        return{
            chekButton:{}
        }
    },
    computed: {
       
    },
// необходимо  добавлять set

    

    methods: {
        //событие выбора ответа
        onChange(e, index){
        if(this.punckt.type === 'radio') {
           this.$set(this.chekButton, 0, index);
       };
        if(this.punckt.type === 'radio') {
           this.$set(this.chekButton, index, index);
       }
    },
        //событие вспытие ответов формы 
        changeAnswer(e){
             console.log('11111');     
            this.$emit('changeAnswers', this.chekButton);
           
        }
    }
}
</script>