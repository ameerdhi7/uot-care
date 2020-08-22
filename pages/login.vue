<template>
  <div class="h-screen login-bg">
    <div class="flex h-full w-full items-center justify-center ">
      <div class="shadow bg-gray-300 md:mb-20 rounded to w-full md:w-1/3 border-solid border-t-4 border-purple  p-8 my-2">
<!--        <form>-->
        <h3 class="text-grey-dark  font-medium font-sans mb-5 leading-normal">Login to Check our latest offers!</h3>
          <div class="mt-3">
            <label>User Name</label>
            <input v-model="credentials.username" type="text" class="border-solid border w-full rounded px-3 py-2"
                   placeholder="username"/>
          </div>
          <div class="mt-3">
            <label>Password</label>
            <input type="password" class="border-solid border w-full rounded px-3 py-2" placeholder="password"
                   v-model="credentials.password"/>
          </div>
          <div class="mt-3">
            <button @click="userLogin" class="bg-teal-600 text-white px-3 py-2 rounded w-full mt-4">Submit</button>
          </div>
<!--        </form>-->
      </div>
    </div>
  </div>
</template>
<script>
  import axios from "axios";
  import qs from "qs";
  import {loginPath} from "../constants";
  export default {
    data() {
      return {
        credentials: {
          username: '',
          password: ''
        }
      }
    },
    methods: {
      async userLogin() {
        try {
          let response = await axios.post(loginPath, qs.stringify(this.credentials));
          console.log(response)
        } catch (err) {
          console.log(err)
        }
      }
    }
  }

</script>
<style scoped>
  .login-bg {
    background: url("/img/doctor-hand-bg.jpg") #4c4c4c;
    background-size: cover;
    background-position: center;
    background-blend-mode: multiply;
  }

</style>
