<template>
<div>
  <button class="end btn" @click.once="game()">click me</button>
    </div>

  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'Result',
  props:['delay'],
methods:{
game(){
    this.end = Date.now()
    this.interval = this.end - this.start
    console.log( this.interval)
    this.$emit("hide" , true )
    this.$emit("score" , this.interval )
}
},
data(){
    return{
    start : null,
    end : 0 ,
    interval : null ,
    hide:true
    }
},
mounted(){
this.start = Date.now()
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

}
.end{
    
position: absolute;
    top: 49%;
    left:20%;
    transform: translate(0, -50%);
    width:60%;
    height:200px;
    font-size:25px;
    color:black;
    border-radius:10px;
    background-color:#FF851B;
}
</style>