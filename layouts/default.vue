<template>
  <div>
    <Navbar/>
    <Nuxt/>
  </div>
</template>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Tajawal&display=swap');
  @import url('https://fonts.googleapis.com/css2?family=Roboto+Mono:ital,wght@1,300&display=swap');
  html {
    font-family: 'Tajawal', sans-serif;
  }
  body {
    background: url("/img/doctor-hand-bg.jpg") #3c3c3c;
    background-position: center;
    background-attachment: fixed;
    background-size: cover;
    background-blend-mode:multiply ;
    /*background: #162e40;*/


    /*background-color: #172e40;*/
    /*background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='100%25' height='100%25' viewBox='0 0 800 400'%3E%3Cdefs%3E%3CradialGradient id='a' cx='396' cy='281' r='514' gradientUnits='userSpaceOnUse'%3E%3Cstop offset='0' stop-color='%23409795'/%3E%3Cstop offset='1' stop-color='%23172e40'/%3E%3C/radialGradient%3E%3ClinearGradient id='b' gradientUnits='userSpaceOnUse' x1='400' y1='148' x2='400' y2='333'%3E%3Cstop offset='0' stop-color='%23409795' stop-opacity='0'/%3E%3Cstop offset='1' stop-color='%23409795' stop-opacity='0.5'/%3E%3C/linearGradient%3E%3C/defs%3E%3Crect fill='url(%23a)' width='800' height='400'/%3E%3Cg fill-opacity='0.4'%3E%3Ccircle fill='url(%23b)' cx='267.5' cy='61' r='300'/%3E%3Ccircle fill='url(%23b)' cx='532.5' cy='61' r='300'/%3E%3Ccircle fill='url(%23b)' cx='400' cy='30' r='300'/%3E%3C/g%3E%3C/svg%3E");*/
    /*background-attachment: fixed;*/
    /*background-size: cover;*/
  }
  #fp-nav ul li a span, .fp-slidesNav ul li a span{
    background: white !important;
  }
  #fp-nav ul li a[class=active] span:nth-child(2){
    height: 12px;
    width: 12px;
    border-radius: 0 !important;
  }
  .scale-hover{
    transition: all .3s;
  }
  .scale-hover:hover{
    transform: scale(1.1);
  }
</style>
