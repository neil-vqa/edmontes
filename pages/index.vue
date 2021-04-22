<template>
  <main class="max-w-screen-xl mx-auto py-5 flex flex-col h-screen">
    <nav class="">
      <nuxt-link to="/" class="heading text-5xl text-gray-400 hover:text-gray-800">edison<span class="text-gray-800 inline-block transition ease-in-out">montes</span></nuxt-link>
    </nav>
    <section class="grid grid-cols-2 h-full">
      <div class="flex flex-col justify-center w-full h-full space-y-10">
        <h1 class="text-5xl">PHOTOS - an inseparable part of our lives</h1>
        <p class="text-3xl">Lorem ipsum dolor sit amet consectetur adipisicing elit. Pariatur, perspiciatis?</p>
      </div>
      <Cards :imgList="pics" />
    </section>
  </main>
</template>

<script>

export default {
  // async asyncData({ $content }) {
	// 	const pics = await $content("gallery").fetch();
		
	// 	return { pics };
	// },
  data() {
    return {
      pics: null
    }
  },
  created() {
    this.fetchFeatures();
  },
  methods: {
    fetchFeatures() {
      this.$axios.get('/features.json').
      then(res => {
        this.pics = res.data;
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