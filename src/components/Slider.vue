<template>
  <div class="clearfix mb-8">
    <h3 class="float-left" v-text="news.title"></h3>
  </div>
  <!-- desktop -->
  <Carousel :settings="settings" class="hidden md:block">
    <Slide v-for="(row, index) in news.content" :key="index">
      <div class="carousel__item news-block mr-8"><a :href="row.url" target="_blank">
        <div class="thumb-block"><img :src="row.thumbnail"></div>
        <div class="content-block">
          <p class="title" v-text="row.title"></p>
          <p v-html="row.date"></p>
          <p v-text="row.intro"></p>
        </div>
      </a></div>
    </Slide>
    <template #addons>
      <navigation />
    </template>
  </Carousel>
  <!-- mobile -->
  <div class="block md:hidden">
    <div class="news-block" v-for="row in news.content"><a :href="row.url" target="_blank">
      <div class="thumb-block"><img class="w-full" :src="row.thumbnail"></div>
      <div class="content-block">
        <p class="title" v-text="row.title"></p>
        <p v-html="row.date"></p>
        <p v-text="row.intro"></p>
      </div>
    </a></div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'
import { Carousel, Navigation, Slide } from 'vue3-carousel'
import 'vue3-carousel/dist/carousel.css'

export default defineComponent({
  name: 'Slider',
  components: {
    Carousel,
    Slide,
    Navigation,
  },
  props: {
    news: Object
  },
  data: () => ({
    settings: {
      itemsToShow: 3,
      snapAlign: 'center',
    }
  }),
})
</script>