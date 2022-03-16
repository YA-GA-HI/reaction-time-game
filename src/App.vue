<template>
<div :class="{'bg-white' : !dark , 'cont':true }">
  <Theme @light="bg"/>
<div class="span"><h2 class="green">Hy there ,</h2><h3 class="f-orange">Are you ready for this time reaction challenge</h3>
<br>
<h3 :class="{'azure':dark , 'text-dark':!dark}">Let's go :)</h3>
</div>
  <Start :dark="dark"/>
  <div class="author">Designed and Developped with <i class="fas fa-heart"></i><br> using Vue By Zenku</div>
  <div class="accounts">
    <a href="https://www.instagram.com/ya_ga_chi/">
    <i class="fab fa-instagram"></i></a>
   <a href="https://github.com/YA-GA-HI"> <i class="fab fa-github"></i></a>
  </div>
</div>
</template>

<script>
import Start from './components/Start.vue'
import Theme from './components/Theme.vue'

export default {
  name: 'App',
  components: {
    Start , Theme
  },
  data(){
    return{
      dark:true
    }
  },
  methods:{
    bg(light){
this.dark = !light
  }}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #3D9970;
  /* margin-top: 60px; */
  height:100%;
  width:100%;
  position:fixed;

}
.span{
  height:30%;
    top: 20%;
    position:absolute;
    width:70%;
    left:15%;
    transform: translate(0, -50%);
    
}
.green{
  color:#2ECC40;
}
.azure{
  color:azure;
}
.black{
  color:black;
}
.bg-white{
  background-color:Azure;
}
.cont{
  height:100%;
  width:100%;
  position:fixed;
}
.author{
  color:#FF851B;
  font-size:17px;
  position:absolute;
  left:8px;
  bottom:8px;
}
.author i{
  color:#2ECC40
}
.accounts{
  position:absolute;
  right:8px;
  bottom:8px;
  display:flex;
}
.accounts a i{
  font-size:40px;
  color:#2ECC40;
  margin-right:10px;
}
</style>
