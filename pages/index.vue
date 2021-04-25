<template>
  <main class="mx-5 max-w-screen-sm lg:max-w-screen-md xl:max-w-screen-xl sm:mx-auto py-5 flex flex-col h-screen">
    <nav class="mb-8 xl:mb-0">
      <nuxt-link to="/" class="heading text-3xl xl:text-5xl text-gray-400 hover:text-gray-800 transition duration-500">edison<span class="text-gray-800 inline-block transition ease-in-out">montes</span></nuxt-link>
    </nav>
    <section class="grid grid-cols-1 xl:grid-cols-2 h-full gap-20 xl:gap-0">
      <div class="flex flex-col justify-center w-full h-full space-y-10">
        <h1 class="text-4xl xl:text-5xl text-center xl:text-left">{{ texts ? texts.heading:'Edison Montes' }}</h1>
        <p class="text-xl xl:text-3xl text-center xl:text-left">{{ texts ? texts.subheading:'Photography portfolio' }}</p>
        <section v-if="texts" class="flex space-x-5 text-gray-400 justify-center xl:justify-start">
          <a :href="texts.social.facebook" target="_blank" class="p-1 rounded-lg transition duration-500 hover:text-white hover:bg-gray-400">
            <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-brand-facebook" width="36" height="36" viewBox="0 0 24 24" stroke-width="1.5" 
              stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
              <path stroke="none" d="M0 0h24v24H0z" fill="none"/>
              <path d="M7 10v4h3v7h4v-7h3l1 -4h-4v-2a1 1 0 0 1 1 -1h3v-4h-3a5 5 0 0 0 -5 5v2h-3" />
            </svg>
          </a>
          <a :href="texts.social.instagram" target="_blank" class="p-1 rounded-lg transition duration-500 hover:text-white hover:bg-gray-400">
            <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-brand-instagram" width="36" height="36" viewBox="0 0 24 24" stroke-width="1.5" 
              stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
              <path stroke="none" d="M0 0h24v24H0z" fill="none"/>
              <rect x="4" y="4" width="16" height="16" rx="4" />
              <circle cx="12" cy="12" r="3" />
              <line x1="16.5" y1="7.5" x2="16.5" y2="7.501" />
            </svg>
          </a>
        </section>
      </div>
      <Cards :imgList="pics" />
    </section>
  </main>
</template>

<script>

export default {
  data() {
    return {
      pics: null,
      texts: null
    }
  },
  created() {
    this.fetchFeatures();
    this.fetchTexts();
  },
  methods: {
    fetchFeatures() {
      this.$axios.get('/static/features.json').
      then(res => {
        this.pics = res.data;
      });
    },
    fetchTexts() {
      this.$axios.get('/static/texts.json').
      then(res => {
        this.texts = res.data;
      });
    }
  }
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

</style>