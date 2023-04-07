<template>
  <footer><div class="clearfix">
    <img src="@/assets/logo-white.svg" class="md:float-left logo">
    <ul class="hidden md:inline-block md:float-right">
      <li class="inline-block mr-2.5"><a :href="'mailto:'+email"><img src="@/assets/icon-mail.svg"></a></li>
      <li class="inline-block"><a :href="fb" target="_blank"><img src="@/assets/icon-facebook.svg"></a></li>
    </ul>
    <nav>
      <ul class="my-12 md:my-0 md:text-center">
        <li class="md:inline-block" v-for="(row, index) in menu" v-text="row.title" @click="goto(row.value)" :class="{'mt-10 md:ml-8 md:mt-0': index !== 0}"></li>
      </ul>
    </nav>
    <ul class="block md:hidden">
      <li class="inline-block mr-4 md:mr-2.5"><a :href="'mailto:'+email"><img src="@/assets/icon-mail.svg"></a></li>
      <li class="inline-block"><a :href="fb" target="_blank"><img src="@/assets/icon-facebook.svg"></a></li>
    </ul>
  </div></footer>
</template>

<script>
export default {
  name: "Footer",
  props: { 
    menu: Array,
    email: String,
    fb: String,
  },
  data() {
    return {}
  },
  methods: {
    goto(selection){
      this.$parent.goto(selection);
    }
  }
};
</script>