<template>
  <carousel 
    :per-page="1" 
    :autoplay="true" 
    :loop="true" 
    :paginationPadding="2" 
    class="flex flex-col justify-center items-center w-full h-full">
    <slide v-for="(item, index) in imgList" :key="index" class="flex flex-col justify-center items-center w-full h-full">
      <div class="relative">
        <img :src="`${source}/static${item.image}`" alt="" class="featured object-contain">
        <div class="opacity-0 hover:opacity-100 transition duration-500 absolute top-0 left-0 w-full h-full">
          <article class="flex flex-col justify-center items-center bg-white bg-opacity-50 h-full px-10 sm:px-20">
            <h1 class="text-xl font-bold">{{ item.title }}</h1>
            <p>{{ item.description }}</p>
          </article>
        </div>
      </div>
    </slide>
  </carousel>
</template>

<script>
export default {
  props: ['imgList'],
  computed: {
    source() {
      return process.env.sourceURL;
    }
  },
}
</script>

<style>
@media screen and (min-width: 640px) {
  .featured {
    box-shadow: rgba(17, 17, 26, 0.1) 0px 8px 24px, rgba(17, 17, 26, 0.1) 0px 16px 56px, rgba(17, 17, 26, 0.1) 0px 24px 80px;
    max-width: 600px;
    max-height: 600px;
  }
}



</style>