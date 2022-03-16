<template>
<div>
<button class="start bg-green btn" v-if="!this.show" @click.once="start()">start</button>
<Result :delay="delay" v-if="this.show" @hide = "hideF" @score ="scoreP"/>
<div :class='{"score":true , "text-dark" :!dark}'>
 <div v-if="this.score == 0">
     No result yet
 </div>
 <div v-if="0<this.score && this.score < 150">
     Your score is : <span class="f-orange"> {{ score }}ms </span> | U are a legend bruh :)
 </div>
 <div v-if="150<this.score && this.score < 300">
     Your score is : <span class="f-orange"> {{ score }}ms </span> | U have a good reaction bruh :)
 </div>
  <div v-if="300<this.score && this.score < 600">
     Your score is : <span class="f-orange"> {{ score }}ms </span> | Almost in time :)
 </div>
<div v-if="600<this.score && this.score < 900">
     Your score is : <span class="f-orange"> {{ score }}ms </span> | Somehow bad reaction , Iwish tha u try again :(
 </div>
 <div v-if="900<this.score ">
     Your score is : <span class="f-orange"> {{ score }}ms </span> | My grandma has a better reaction than yours :|
 </div>
 </div>   
 </div>
</template>

<script>
import Result from './Result.vue'

export default {
  name: 'App',
  components: {
    Result
  },
  props:['dark'],
  data(){
      return {
          delay:0 ,
          show:false,
          score:0
      }
  },
  methods:{
      start(){
          let x = Math.random() * 4000 
          console.log(x)
this.delay = x
setTimeout(()=>{
        this.show = true
    },this.delay)
      } ,
      hideF(hide){
          this.show = !hide ;
      } ,
      scoreP(interval){
          this.score = interval ;
      }
  }
}
</script>

<style>
/* .s{
    height:40%;
    width:100%;
} */
.start{
    position: absolute;
    top: 43%;
    left:30%;
    transform: translate(0, -50%);
    width:40%;
    height:30px;
    font-size:25px;
    line-height:2px;
    color:black;
    border-radius:10px;
    justify-content:center;
}
@media only screen and (max-width: 400px) {
  .score div{
      margin-top:20px;
    font-size:20px;

}
}
.score{
    position: absolute;
    top: 75%;
    left:15%;
    width:70%;
    transform: translate(0, -50%);
    font-size:30px;
    color:Azure;
}
.score div .orange{
   position:relative
}
.score div {
   position:relative
}
.bg-navy{
    background-color:#001f3f;
}
.bg-green{
    background-color:#2ECC40;
}
.f-orange{
    color:#FF851B;
}
</style>
