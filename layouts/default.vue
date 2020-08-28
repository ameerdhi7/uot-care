<template>
  <div>
    <Navbar/>
    <Nuxt/>
  </div>
</template>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Tajawal&display=swap');
  html {
    font-family: 'Tajawal', sans-serif;
  }
  body {
    background: url("/img/doctor-hand-bg.jpg") #3c3c3c;
    background-position: center;
    background-attachment: fixed;
    background-size: cover;
    background-blend-mode: multiply;
  }

  #fp-nav ul li a span, .fp-slidesNav ul li a span {
    background: white !important;
  }

  #fp-nav ul li a[class=active] span:nth-child(2) {
    height: 12px;
    width: 12px;
    border-radius: 0 !important;
  }

  .scale-hover {
    transition: all .3s;
  }

  .scale-hover:hover {
    transform: scale(1.1);
  }
</style>
