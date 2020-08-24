<template>
    <div class="section">
      <div class="container mx-auto flex px-5 pb-24  items-center justify-center flex-col">
        <div class="text-center lg:w-2/3 w-full">
          <h1 class="hero-title sm:text-4xl text-3xl lg:text-6xl   uppercase font-medium font-extrabold text-white">uot care</h1>
          <p class="mb-8 text-white text-3xl leading-relaxed">Browse The Hospitals Offers and get the benefits!</p>
          <div class="flex justify-center">
            <button class="inline-flex text-white
            -teal-500 border-0 py-2 rounded-lg px-12 scale-hover focus:outline-none bg-teal-900 rounded  text-lg"><Nuxt-link  to="/login" >Sign in</Nuxt-link></button>
            <button class="ml-4 inline-flex scale-hover text-gray-700 rounded-lg bg-gray-200 border-0 py-2 px-12 text-teal-900 focus:outline-none hover:bg-gray-300 rounded text-lg">
              <a data-menuanchor="register" href="/#register">Sign up</a></button>
          </div>
        </div>
      </div>

    </div>
</template>
<style scoped>
  .hero-title{
    font-size: 6rem;
    /*filter: drop-shadow(0px 0px 6px #3d3d3d);*/
  }
</style>
