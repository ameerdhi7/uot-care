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
    /*background: url("/img/doctor-pills-bg.jpg");*/
    background-position: center;
    background-attachment: fixed;
    background-size: cover;
    background: #162e40;
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
