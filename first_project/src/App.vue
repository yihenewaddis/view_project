<template>
  <div class="first">
    <div>
      <h1>reaction timer is displayed here</h1>
      <button @click="play" :disabled="isPlay" class="button">Play</button>
      <p>the score you get is {{score}} ms</p>
      <p>this is the value</p>
      <Block v-if="isPlay" :delay="delay" @end="endGame"/>
      <Signup/>
    </div>
  </div>
</template>
<script>
import Block from './components/Block.vue'
import Signup from './components/Signup.vue'
export default{
  components:{
    Block,Signup
  },
  data(){
    return{
    isPlay:false,
    delay:null,
    score:0
    }
  },
  methods:{
    play(){
      this.isPlay = true
      this.delay = 2000+Math.random()*5000
    },
    endGame(reactiontimer){
        this.score = reactiontimer,
        this.isPlay = false
    }
  }
}
</script>
<style scoped>

.first{
  display: flex;
  justify-content: center;
  margin-top: 40px;
  width: 500px;
  height: 500px;
  margin: auto;
}
.button{
  background-color: rgb(12, 196, 238);
  border: none;
  padding: 5px 15px;
  border-radius: 5px;
  color: white;
  font-weight: bold;
  cursor: pointer;
}
.button[disabled]{
  cursor: not-allowed;
  opacity: .7;
}

</style>
