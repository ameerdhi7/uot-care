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
    data() {
      return {
        options: {
          licenseKey: '298390128390128',
          menu: '#menu',
          anchors: ['home', 'register', 'offers'],
          navigation: true,
          scrollingSpeed:1000,
          keyboardScrolling:true

        },

      }
    },
    fetchOnServer: false,
    created() {
      // this.$axios.$get(universitiesPath).then(response=>console.log(response.data))
    }
  }

</script>

<style>

</style>
