<template>
    <div>  
    <h2>{{punckt.title}}</h2>
    
    <div class="form-check">
      <div v-for="(answer, index) in punckt.answers" :key="index">  
        <label class="form-check-label">
            <input :type="punckt.type" class="form-check-input"   :value="answer">
            {{answer}}
        </label>
      </div>
    </div>
    </div>
</template>

<script>
export default {
    props:["punckt"],
    data(){
        return{
            
        }
    }
}
</script>