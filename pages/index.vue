<template>
  <main class="max-w-screen-xl mx-auto py-5 flex flex-col h-screen">
    <nav class="">
      <nuxt-link to="/" class="heading text-5xl text-gray-400 hover:text-gray-800">edison<span class="text-gray-800 inline-block transition ease-in-out">montes</span></nuxt-link>
    </nav>
    <section class="grid grid-cols-2 w-full h-full">
      <div class="flex flex-col justify-center w-full h-full space-y-10">
        <h1 class="text-5xl">PHOTOS - an inseparable part of our lives</h1>
        <p class="text-3xl">Lorem ipsum dolor sit amet consectetur adipisicing elit. Pariatur, perspiciatis?</p>
      </div>
      <div class="flex flex-col justify-center items-center w-full h-full relative">
        <img src="/sample/nana.jpg" alt="" class="show w-11/12 object-cover">
        <div class="opacity-0 hover:opacity-100 transition duration-500 absolute top-0 left-0 h-full w-full">
          <article class="flex flex-col justify-center items-center bg-white bg-opacity-50 h-full px-20">
            <h1 class="text-xl font-bold">Lorem ipsum, dolor sit amet consectetur adipisicing.</h1>
            <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Qui, atque harum. Minima adipisci ab laudantium?</p>
          </article>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
export default {

}
</script>

<style>
.heading {
  font-family: 'Suranna', serif;
}

.heading:hover > span {
  transform: translateX(5px);
  transition-duration: 500ms;
}

.show {
  box-shadow: rgba(17, 17, 26, 0.1) 0px 8px 24px, rgba(17, 17, 26, 0.1) 0px 16px 56px, rgba(17, 17, 26, 0.1) 0px 24px 80px;
}



</style>