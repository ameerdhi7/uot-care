<template>
  <ul id="menu" class="mx-auto">
    <li id="logo" class="text-white mr-3 text-lg md:border-r px-2 md:border-gray-40 uppercase font-extrabold"
        style="font-family: 'Roboto Mono', monospace;">Uot care
    </li>
    <li data-menuanchor="home" class="mr-5 active text-white scale-hover"><a href="/#home">Home</a></li>
    <li data-menuanchor="register" class="mr-5 text-white scale-hover"><NLink to="/login">Sign in</NLink></li>
    <li data-menuanchor="offers" class="mr-5 text-white scale-hover"><a href="/#offers">Browse Offers</a></li>
  </ul>
</template>
<style scoped>
  #menu-line {
    position: absolute;
    bottom: -4px;
    left: 0;
    width: 159px;
    height: 2px;
    background: #fff
  }

  #menu {
    position: fixed;
    top: 20px;
    left: 20px;
    z-index: 70;
    -webkit-font-smoothing: antialiased;
    -moz-font-smoothing: antialiased;
    letter-spacing: 1px;
    font-size: 1.1em
  }

  #menu li {
    display: inline-block;
    margin: 10px 0;
    position: relative
  }

  #menu a {
    color: #fff;
    padding: 0 1.1em 1.1em 1.1em
  }

  #menu li.active a:after {
    content: '';
    margin: 0 1.1em 0 1.1em;
    height: 2px;
    background: #fff;
    display: block;
    position: absolute;
    bottom: -6px;
    left: 0;
    right: 0;
    display: block
  }

  @media (max-width: 600px) {
    #menu {
      position: fixed;
      bottom: 0px !important;
      top: initial !important;
      left: 0px !important;
      width: 100%;
      background: #234e52;
      padding: 0.3rem;
      display: flex;
      justify-content: center;
      border-top-width: 1px;
    }
    #logo {
      display: none !important;
    }

  }
</style>
