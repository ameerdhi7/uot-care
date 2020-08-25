<template>
  <div>
    <full-page :options="options">
      <HeroSection/>
      <Register/>
      <Hospitals/>
    </full-page>
  </div>
</template>

<script>
  import {loginPath, universitiesPath} from "../constants";

  export default {
    name: 'index',
    data() {
      return {
        options: {
          licenseKey: '298390128390128',
          menu: '#menu',
          anchors: this.$auth.loggedIn ? ['home', 'offers'] : ['home', 'register', 'offers'],
          navigation: true,
          scrollingSpeed: 1000,
          keyboardScrolling: true

        },
      }
    },
  }

</script>
