<template>
    <div>
        <h2>{{title}}</h2>
        <hr>
        <div class= "form-group"
            v-for = "(answer, index) in answers"
            :key = "index"
          
         style="text-align:left;"         
        >
            <input :type = "typeInput"
                :value = "answer"
                v-model = "ans[num]"  
            >
            <label > {{answer}}  </label>   
        </div>
        <h3>{{ ans[num] }}</h3>
    </div>
</template>

<script>

export default {

    props: ['title', 'answers', 'typeInput', 'num'],

    data(){
        return{
            ans:['', Array()]

        }
    }
}
</script>