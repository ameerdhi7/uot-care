<template>
  <div class="h-screen bg-black">
      <form @submit="userLogin">
        <div class="shadow bg-gray-300 rounded to w-full md:w-1/4 border-solid border-t-4 border-purple p-6 my-2">
          <h3 class="text-grey-dark text-sm font-medium font-sans leading-normal">Check our latest offers!</h3>
          <div class="mt-3">
          <label>Email</label>
          <input v-model="credentials.email" type="email" class="border-solid border w-full rounded px-3 py-2" placeholder="Email"/>
          </div>
          <div class="mt-3">
            <label>Password</label>
            <input type="password" class="border-solid border w-full rounded px-3 py-2" placeholder="password" v-model="credentials.password"/>
          </div>
          <div class="mt-3">
          <button type="submit" class="bg-teal-600 text-white px-3 py-2 rounded w-full mt-4">Submit</button>
          </div>
        </div>
      </form>
    </div>
</template>
<script>
  export default {
    data() {
      return {
        credentials: {
          email: '',
          password: ''
        }
      }
    },
    methods: {
      async userLogin() {
        try {
          let response = await this.$auth.loginWith('local', {data: this.credentials});
          console.log(response)
        } catch (err) {
          console.log(err)
        }
      }
    }
  }

</script>
