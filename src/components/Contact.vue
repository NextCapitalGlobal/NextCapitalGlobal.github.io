<template>
  <div class="inquiry-block clearfix">
    <h3 v-text="inquiry.title"></h3>
    <a :href="'mailto:'+email" class="float-right btn-white hidden md:block" v-text="inquiry.btn"></a>
    <p class="mt-5" v-text="inquiry.intro"></p>
    <a :href="'mailto:'+email" class="btn-white mt-6 inline-block md:hidden" v-text="inquiry.btn"></a>
  </div>
  <div class="subscribe-block">
    <h3 class="m-0 mb-8" v-text="subscribe.title"></h3>
    <label class="subscribe-form">
      <img src="@/assets/icon-mail-border.svg" class="pointer-events-none icon">
      <input type="email" :placeholder="subscribe.email_default_msg" class="md:w-1/2">
      <a class="btn-white hidden md:inline-block" :href="subscribe.link" v-text="subscribe.btn"></a>
    </label>
    <a class="mt-3 btn-white block md:hidden" :href="subscribe.link" v-text="subscribe.btn"></a>
  </div>
</template>

<script>
export default {
  name: "Contact",
  props: { 
    inquiry: Object,
    subscribe: Object,
    email: String
  },
  data() {
    return {}
  },
  methods: {
  }
};
</script>