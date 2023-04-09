<template>
  <p class="mb-2" v-text="content.name"></p>
  <h1 class="mb-6" v-html="content.title"></h1>
  <div class="md:w-3/5">
    <p v-text="content.desc"></p>
  </div>
</template>

<script>
export default {
  name: "Intro",
  props: { 
    content: Object
  },
  data() {
    return {}
  },
  methods: {
  }
};
</script>