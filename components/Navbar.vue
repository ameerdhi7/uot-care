<template>
  <ul id="menu" class="mx-auto">
    <li id="logo" class="text-white mr-3 text-lg md:border-r px-2 md:border-gray-40 uppercase font-extrabold"
        style="font-family: 'Roboto Mono', monospace;">Uot care
    </li>
    <li data-menuanchor="home" class="mr-5 active text-white scale-hover">
      <NLink to="/#home">Home</NLink>
    </li>
    <li v-if="!this.$auth.loggedIn" data-menuanchor="register" class="mr-5 text-white scale-hover">
      <NLink to="/login">Sign in</NLink>
    </li>
    <li data-menuanchor="offers" class="mr-5 text-white"><a href="/#offers">Browse Offers</a></li>
    <li id="logout-button" v-if="this.$auth.loggedIn" @click="logoutButtonOpened=!logoutButtonOpened"  class="md:fixed  md:right-0 text-white scale-hover">
    <div class="flex">
      <svg  class="fill-current  w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
        <path d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"/>
      </svg>
      {{this.$auth.user.username}}
    </div>
      <button @click="this.$auth.logout()" v-show="logoutButtonOpened" href=""  class="bg-teal-900 logout-trans w-full rounded p-1">Logout</button>
    </li>
  </ul>
</template>
<script>
  export default {
    data(){
      return {
        logoutButtonOpened:false
      }
    }
  }
</script>
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
@media (min-width: 768px) {
  #logout-button {
    margin: 0 !important;
    position: fixed;
    top: 34px;
  }

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
  .logout-trans{
    transition: all .6s;
  }
</style>
