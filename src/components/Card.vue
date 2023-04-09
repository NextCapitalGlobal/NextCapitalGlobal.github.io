<template>
  <h3 class="text-center" v-html="card.title"></h3>
  <div class="intro-block">
    <div class="cover-block"><img src="@/assets/card-screenshot.svg"></div>
    <div class="content-block">
      <p v-for="row in card.desc" v-text="row"></p>
      <p></p>
      <button class="btn-black inline-block mt-6" v-text="card.btn"></button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: { 
    card: Object
  },
  data() {
    return {}
  },
  methods: {
  }
};
</script>