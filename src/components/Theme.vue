<template>
  <div class="theme bg-white">
      <div class="first" @click="change()">
          <i class="far fa-moon orange"></i>
        </div>
  <div class="second" @click="change()">
        <i class="fas fa-circle orange b"></i>
  </div>
   <div class="butn" :class="{light:light}"></div>
  </div>
     
</template>

<script>
export default {
    name:"Theme",
data(){
    return {
        light:false
    }
} ,
methods:{
    change(){
        this.light = !this.light
        this.$emit('light',this.light)
            
    }
}
}
</script>

<style>
.theme{
    height:40px;
    width:80px;
    position:absolute;
    top:10px;
    left:20px;
    padding:4px;
    border-radius:20px;
    border:1px solid black;
    /* padding-bottom:5px; */
    
}
.butn{
    height:35px;
    position:relative;
    width:35px;
    border-radius:50%;
    background-color:black;
    z-index:1;
    margin-top:-2px;
    /* margin-bottom:10px; */
    /* margin-left:10px; */
}
.first{
    height:35px;
    position:relative;
    width:35px;
    border-radius:50%;
    float:left;
    z-index:2;
}
.second{
    height:35px;
    position:relative;
    width:35px;
    border-radius:50%;
    float:right;
    z-index:2;
}
.orange{
    color:#FF851B;
    padding-top:8px;
}
.b{
    font-size:22px;
    padding-top:5px;
}
.light{
    margin-left:35px;
}
</style>