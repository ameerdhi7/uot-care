<template>
  <div class="w-full section h-screen flex items-center justify-center" style="background: #162e40">
    <div style="height: 77%" class="hospital-section-bg  flex justify-center items-center  w-full">
      <div class="rounded p-12 mx-3 md:mx-0 my-auto  bg-gray-300">
        <h1 class="text-3xl ">Select a University to Browse its offers</h1>
        <div class="flex items-center justify-center  flex-wrap">
          <div class="inline-block relative w-64 md:mr-1  mb-3 md:mb-0">
            <select v-model="selectedHospital"
                    class="block rounded-lg appearance-none w-full bg-white border border-gray-400 hover:border-gray-500 px-4 py-2 pr-8 rounded shadow leading-tight focus:outline-none focus:shadow-outline">
              <option v-for="hospital in hospitals" :value="hospital.id">{{hospital.name}}</option>
            </select>
            <div class="pointer-events-none absolute inset-y-0 right-0 flex items-center px-2 text-gray-700">
              <svg class="fill-current h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
                <path d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"/>
              </svg>
            </div>
          </div>
            <nuxt-link class="inline-flex text-white
             border-0 py-2  rounded-lg px-12 scale-hover focus:outline-none bg-teal-900 rounded  text-lg"
                       :to="hospitalLink">Browse
            </nuxt-link>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
  import {hospitalsPath} from "../constants";

  export default {
    data() {
      return {
        hospitals: [],
        selectedHospital: null,
      }
    },
    methods: {
      async fetchHospitals() {
        try {
          const response = await this.$axios.$get(hospitalsPath);
          this.hospitals = response.data;
        } catch (e) {
          console.log(e)
        }
      }
    },
    computed: {
      hospitalLink: function () {
        return this.selectedHospital ? `/hospitals/${this.selectedHospital}` : '#';
      },
    },
    mounted() {
      this.fetchHospitals()
    }
  }
</script>
<style>
  .hospital-section-bg {
    background: url('/img/pill-bg.jpg') #282828;
    background-size: cover;
    background-position: center;
    background-blend-mode: multiply;
  }
</style>
