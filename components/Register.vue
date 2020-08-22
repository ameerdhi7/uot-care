<template>
  <div class="absolute bg-gray-200 section w-full h-full">
    <div
      class="absolute  register-bg w-full h-full">
    </div>
    <div class="container mx-auto px-4 h-full">
      <div class="flex content-center items-center justify-center h-full">
        <div class="w-full lg:w-1/2 px-4">
          <div
            class="relative flex flex-col min-w-0 break-words w-full mb-6 bg-gray-300 rounded-lg  border-0"
          >
            <div class="rounded-t mb-0 px-6 py-6">
              <div class="text-center mb-3">
                <h5 class="text-gray-600  font-bold">
                  Register to Uot Care to get students package
                </h5>
              </div>
              <hr class="mt-3 border-b-1 border-gray-400"/>
            </div>
            <div class="flex-auto px-4 lg:px-10 py-10 pt-0">
              <form class="w-full max-w-lg">
                <div class="flex flex-wrap -mx-3 mb-1">
                  <div class="w-full md:w-1/2 px-3 mb-3 md:mb-0">
                    <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                           for="grid-first-name">
                      First Name
                    </label>
                    <input required v-model="credentials.firstName"
                           class="appearance-none  block w-full bg-gray-200 text-gray-700 border  rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
                           id="grid-first-name" type="text" placeholder="Jane">
                    <!--                    <p class="text-red-500 text-xs italic">Please fill out this field.</p>-->
                  </div>
                  <div class="w-full md:w-1/2 px-3">
                    <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                           for="grid-last-name">
                      Last Name
                    </label>
                    <input v-model="credentials.lastName"
                           class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
                           id="grid-last-name" type="text" placeholder="Doe">
                  </div>
                </div>
                <div class="flex flex-wrap -mx-3 mb-1">
                  <div class="w-full md:w-1/2 px-3 mb-3 md:mb-0">
                    <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                           for="email">
                      Email
                    </label>
                    <input required v-model="credentials.email"
                           class="appearance-none block w-full bg-gray-200 text-gray-700 border  rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
                           id="email" type="email" placeholder="email">
                    <!--                    <p class="text-red-500 text-xs italic">Please fill out this field.</p>-->
                  </div>
                  <div class="w-full md:w-1/2 px-3">
                    <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                           for="username">
                      Username
                    </label>
                    <input v-model="credentials.username"
                           class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
                           id="username" type="text" placeholder="Doe">
                  </div>
                </div>


                <div class="flex flex-wrap -mx-3 mb-1">
                  <div class="w-full px-3">
                    <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                           for="grid-password">
                      Password
                    </label>
                    <input v-model="credentials.password"
                           class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
                           id="grid-password" type="password" placeholder="******************">
                    <p class="text-gray-600 text-xs italic">Make it as long and as crazy as you'd like</p>
                  </div>
                </div>
                <div class="flex flex-wrap -mx-3">
                  <div class="w-full px-3  md:mb-0">
                    <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="grid-state">
                      Select a University
                    </label>
                    <div class="relative">
                      <select v-model="credentials.universityName"
                              class="block appearance-none w-full bg-gray-200 border border-gray-200 text-gray-700 py-3 px-4 pr-8 rounded leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
                              id="grid-state">
                        <option v-for="university in universities">{{university.name}}</option>
                      </select>
                      <div class="pointer-events-none absolute inset-y-0 right-0 flex items-center px-2 text-gray-700">
                        <svg class="fill-current h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
                          <path d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"/>
                        </svg>
                      </div>
                    </div>
                  </div>
                  <button
                    @click="registerUser"
                    class="bg-teal-600 text-white mt-2 active:bg-gray-700 text-sm font-bold uppercase px-6 py-3 rounded shadow hover:shadow-lg outline-none focus:outline-none mr-1  w-full"
                    type="button"
                    style="transition: all 0.15s ease 0s;"
                  >
                    Register
                  </button>

                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

</template>
<script>
  import {registerPath, universitiesPath} from "../constants";
  import qs from 'qs'

  export default {
    data() {
      return {
        universities: [],
        credentials: {
          firstName: '',
          lastName: '',
          username: '',
          universityName: '',
          email: '',
          password: '',
        }
      }
    },
    methods: {
      async fetchUniversities() {
        try {
          const response = await this.$axios.$get(universitiesPath);
          this.universities = response.data;
        } catch (err) {
          console.log(err)
        }
      },
      handResponseMessage(message) {
        if (message.includes("Verify"))
          this.$swal(
            `'Good job!'${this.credentials.username}`,
            `Verification email has sent to ${this.credentials.email} . Verify your account to use Health Care App.`,
            'success'
          );
        else
          this.$swal({
            icon: 'error',
            title: 'Oops...',
            text: message,
          });
      },
      async registerUser() {
        try {
          const response = await this.$axios.$post(registerPath, qs.stringify(this.credentials));
          this.handResponseMessage(response.message)
        } catch (err) {
          console.log(err)
        }
      }
    },
    mounted() {
      this.fetchUniversities()
    }
  }
</script>
<style>
  .register-bg {
    background-size: 100%;
    background: #162e40;
    background-repeat: no-repeat;
    background-image: url('/img/register-background.png');
  }
</style>
