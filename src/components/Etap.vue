<template>
    <div> 
        <h2>{{ etap.title }}</h2>
        <div class="form-check" style= "text-align: left">
            <label  class="form-check-label" style = "display:block"
                 v-for="(question, indexQuestion) in etap.answers"  :key="indexQuestion">  
                <input  class = "form-check-input" 
                    :type="etap.type" 
                    :value="question"
                    @change = "selectOn(indexQuestion)"
                >
            {{question}}
            </label>
        </div> 
    </div>   
</template>
<script>
    export default {
        props:['etap'],
        data(){
            return {

            }
        },
        computed:{

        },
        methods:{
            selectOn(index) {console.log(index)}
        }
    }
</script>
