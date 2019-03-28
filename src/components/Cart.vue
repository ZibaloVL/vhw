<template>
    <div>  
        <form action="">
            <h2>{{punckt.title}}</h2>
            <hr>
            <div class="form-check">
                <div v-for="(answer, index) in punckt.answers" :key="index">  
                    <label class="form-check-label">
                        <input :type="punckt.type" class="form-check-input"   :value="answer">
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
    props:["punckt"],
    data(){
        return{
            
        }
    }
}
</script>