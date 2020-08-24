<template>
  <section class="text-gray-700  overflow-hidden">
    <div class="container px-5 py-24 mx-auto">
      <div class="flex flex-col text-center w-full mb-20">
        <h1 class="sm:text-4xl text-3xl font-medium title-font mb-2 text-white">{{hospital.name}}</h1>
        <p class="lg:w-2/3 mx-auto leading-relaxed text-base">Whatever cardigan tote bag tumblr hexagon brooklyn
          asymmetrical.</p>
      </div>
      <div class="flex flex-wrap -m-4">

        <div v-for="offer in hospital.offersDetails" class="p-4  xl:w-1/4 md:w-1/2 w-full">
          <div class="h-full p-6 rounded-lg border-2 border-teal-500 bg-black flex flex-col relative overflow-hidden">
            <span class="bg-teal-900 text-white px-3 py-1 tracking-widest text-xs absolute right-0 top-0 rounded-bl">{{offer.itemPrice}}$</span>
            <h2 class="text-sm tracking-widest title-font mb-1 font-medium">PRO</h2>
            <h1 class="text-5xl text-white leading-none flex items-center pb-4 mb-4 border-b border-gray-200">
              <span>%{{offer.amount}}</span>
              <span class="text-lg ml-1 font-normal text-white">/mo</span>
            </h1>

            <p class="flex items-center text-gray-600 mb-6">
              {{offer.description}}
            </p>
            <button

              class="flex items-center mt-auto text-white bg-teal-900 border-0 py-2 px-4 w-full focus:outline-none hover:bg-teal-600 rounded">
              Get Benefits
              <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                   class="w-4 h-4 ml-auto" viewBox="0 0 24 24">
                <path d="M5 12h14M12 5l7 7-7 7"></path>
              </svg>
            </button>
            <p class="text-xs text-gray-500 mt-3">Literally you probably haven't heard of them jean shorts.</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
  import {offersPath} from "../../constants";
  import qs from 'qs';

  export default {
    data() {
      return {
        hospital: [],
      }
    },
    methods: {
      async fetchHospitalOffers() {
        try {
          const response = await this.$axios.$post(offersPath, qs.stringify({hospitalId: this.$route.params.id}));
          this.hospital = response.data;
          console.log(response)
        } catch (e) {
          console.log(e)
        }

      },
      // async checkout(offerId) {
      //   try {
      //     const response = await this.$axios.$post(offersPath, qs.stringify({universityName: this.hospital.name,offerId:offerId}));
      //     this.hospital = response.data;
      //     console.log(response)
      //   } catch (e) {
      //     console.log(e)
      //   }
      //
      // }
    },
    mounted() {
      this.fetchHospitalOffers();
    },
  }
</script>
<style>
  body{
    background-color: #a8a8a8;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='920' height='920' viewBox='0 0 200 200'%3E%3Cdefs%3E%3ClinearGradient id='a' gradientUnits='userSpaceOnUse' x1='88' y1='88' x2='0' y2='0'%3E%3Cstop offset='0' stop-color='%230c1a24'/%3E%3Cstop offset='1' stop-color='%23142939'/%3E%3C/linearGradient%3E%3ClinearGradient id='b' gradientUnits='userSpaceOnUse' x1='75' y1='76' x2='168' y2='160'%3E%3Cstop offset='0' stop-color='%235e5e5e'/%3E%3Cstop offset='0.09' stop-color='%23767676'/%3E%3Cstop offset='0.18' stop-color='%23858585'/%3E%3Cstop offset='0.31' stop-color='%23909090'/%3E%3Cstop offset='0.44' stop-color='%23999999'/%3E%3Cstop offset='0.59' stop-color='%23a0a0a0'/%3E%3Cstop offset='0.75' stop-color='%23a5a5a5'/%3E%3Cstop offset='1' stop-color='%23a8a8a8'/%3E%3C/linearGradient%3E%3Cfilter id='c' x='0' y='0' width='200%25' height='200%25'%3E%3CfeGaussianBlur in='SourceGraphic' stdDeviation='12' /%3E%3C/filter%3E%3C/defs%3E%3Cpolygon fill='url(%23a)' points='0 174 0 0 174 0'/%3E%3Cpath fill='%23000' fill-opacity='0.52' filter='url(%23c)' d='M121.8 174C59.2 153.1 0 174 0 174s63.5-73.8 87-94c24.4-20.9 87-80 87-80S107.9 104.4 121.8 174z'/%3E%3Cpath fill='url(%23b)' d='M142.7 142.7C59.2 142.7 0 174 0 174s42-66.3 74.9-99.3S174 0 174 0S142.7 62.6 142.7 142.7z'/%3E%3C/svg%3E");
    background-attachment: fixed;
    background-repeat: no-repeat;
    background-position: top left;
  }

</style>
