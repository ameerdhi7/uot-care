<template>
  <div class="absolute bg-gray-200 section w-full h-full">
    <div
      class="absolute top-0 register-bg w-full h-full">
    </div>
    <div class="container mx-auto px-4 h-full">
      <div class="flex content-center items-center justify-center h-full">
        <div class="w-full lg:w-4/12 px-4">
          <div
            class="relative flex flex-col min-w-0 break-words w-full mb-6 bg-gray-300 rounded-lg  border-0"
          >
            <div class="rounded-t mb-0 px-6 py-6">
              <div class="text-center mb-3">
                <h5 class="text-gray-600  font-bold">
                  Register to Uot Care to get students package
                </h5>
              </div>
              <hr class="mt-6 border-b-1 border-gray-400"/>
            </div>
            <div class="flex-auto px-4 lg:px-10 py-10 pt-0">
              <div class="text-gray-500 text-center mb-3 font-bold">
                <!--                <small>Or sign in with credentials</small>-->
              </div>
              <form>
                <div class="relative w-full mb-3">
                  <label
                    class="block uppercase text-gray-700 text-xs font-bold mb-2"
                    for="grid-password"
                  >Full Name</label
                  ><input
                  type="email"
                  class="px-3 py-3 placeholder-gray-400 text-gray-700 bg-white rounded text-sm shadow focus:outline-none focus:shadow-outline w-full"
                  placeholder="full name"
                  style="transition: all 0.15s ease 0s;"
                />
                </div>
                <div class="relative w-full mb-3">
                  <label
                    class="block uppercase text-gray-700 text-xs font-bold mb-2"
                    for="grid-password"
                  >Email</label
                  ><input
                  type="email"
                  class="px-3 py-3 placeholder-gray-400 text-gray-700 bg-white rounded text-sm shadow focus:outline-none focus:shadow-outline w-full"
                  placeholder="Email"
                  style="transition: all 0.15s ease 0s;"
                />
                </div>
                <div class="relative w-full mb-3">
                  <label
                    class="block uppercase text-gray-700 text-xs font-bold mb-2"
                    for="grid-password"
                  >Password</label
                  ><input
                  type="password"
                  class="px-3 py-3 placeholder-gray-400 text-gray-700 bg-white rounded text-sm shadow focus:outline-none focus:shadow-outline w-full"
                  placeholder="Password"
                  style="transition: all 0.15s ease 0s;"
                />
                </div>
                <div class="text-center mt-6">
                  <button
                    class="bg-teal-600 text-white active:bg-gray-700 text-sm font-bold uppercase px-6 py-3 rounded shadow hover:shadow-lg outline-none focus:outline-none mr-1 mb-1 w-full"
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
<style>
  .register-bg {
    background-size: 100%;
    background: #162e40;
    background-repeat: no-repeat;
    background-image: url('/img/register-background.png');
    /*filter: hue-rotate(381deg);*/
  }
</style>
