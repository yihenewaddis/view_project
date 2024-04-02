<template>
    <div>
        <div class="block" v-if="ShowBlock" @click="stoptimer">
        </div>
    </div>
</template>

<script>
export default {
props:['delay'],
data(){
    return{
        ShowBlock: false,
        setInterval:null,
        reactionTime:0,
    }
},
// this function fire when this component is mount
mounted(){
    setTimeout(()=>{
        this.ShowBlock = true
        this.starttimer()
    },this.delay)
},
//this function is called when the variable is changed
updated(){
},
unmounted(){
    
},
methods:{
    starttimer(){
    this.setInterval = setInterval(()=>{
        this.reactionTime +=10
        },10)
    },
    stoptimer(){
    clearInterval(this.setInterval)
    this.$emit('end',this.reactionTime)
    this.ShowBlock = false
    }
}
}
</script>

<style>
.block{
    width: 300px;
    height: 300px;
    background-color: rgb(12, 196, 238);
    margin-top: 20px;
}
</style>