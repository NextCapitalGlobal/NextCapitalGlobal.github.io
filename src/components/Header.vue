<template>
  <div class="header" ref="header" :class="{'active': isFixed}"><div class="inner clearfix">
    <a href="/" class="float-left logo"><img src="@/assets/logo.svg"></a>

    <div class="hidden md:block float-right">
      <div class="lang-block inline-block mr-6">
        <img class="inline-block" src="@/assets/icon-lang.svg">
        <select :value="lang" @change="updateLang($event.target.value)">
          <option v-for="row in langs" v-text="row.title" :value="row.value"></option>
        </select>
      </div>
      <a :href="'mailto:'+email" class="btn-black inline-block" v-text="contact_btn"></a>
    </div>
    <nav class="hidden md:block">
      <ul class="menu text-center">
        <li class="inline-block" v-for="(row, index) in menu" v-text="row.title" @click="goto(row.value)" :class="{'ml-8': index !== 0}"></li>
      </ul>
    </nav>
    <button class="block md:hidden float-right btn-mobile-menu" @click="toggleMobileMenu('open')"><img src="@/assets/icon-menu.svg"></button>
  </div></div>
  <div class="block md:hidden mobile-menu-container" ref="mobileMenu">
    <button class="block md:hidden float-right btn-mobile-menu" @click="toggleMobileMenu('close')"><img src="@/assets/icon-close.svg"></button>
    <nav>
      <ul class="menu mt-8 mb-8">
        <li v-for="(row, index) in menu" v-text="row.title" @click="goto(row.value)" :class="{'mt-8': index !== 0}"></li>
      </ul>
    </nav>
    <div class="lang-block">
      <img class="inline-block" src="@/assets/icon-lang.svg">
      <select :value="lang" @change="$emit('lang', $event.target.value)">
        <option v-for="row in langs" v-text="row.title" :value="row.value"></option>
      </select>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",
  props: { 
    lang: String,
    langs: Array,
    menu: Array,
    email: String,
    contact_btn: String
  },
  data() {
    return {
      isFixed: false,
      device: "desktop",
    }
  },
  mounted() {
    this.detectDevice();
  },
  created() {
    window.addEventListener('resize', this.detectDevice);
    window.addEventListener('scroll', this.scrollHeight);
  },
  destroyed() {
    window.removeEventListener('resize', this.detectDevice);
    window.removeEventListener('scroll', this.scrollHeight);
  },
  methods: {
    detectDevice() {
      this.device = (window.innerWidth > 767) ? 'desktop' : 'mobile';

      var offset = 0;
      if(this.device === 'desktop') {
        offset = this.$refs.header.clientHeight;
      }

      document.body.style.paddingTop = offset+"px";
    },
    scrollHeight() {
      var offset = this.$refs.header.clientHeight;
      var scrolled = document.scrollingElement.scrollTop;

      if(this.device === 'desktop') {
        this.isFixed = (scrolled >= offset) ? true : false;
      } else {
        this.isFixed = (scrolled >= 50) ? true : false;
      }
    },
    goto(selection){
      if(this.device === 'mobile') {
        this.toggleMobileMenu('close');
      }

      this.$parent.goto(selection, this.$refs.header.clientHeight);
    },
    toggleMobileMenu(type) {
      if(type === 'open') {
        document.body.style.overflowY = "hidden";
        this.$refs.mobileMenu.classList.add('active');
      } else {
        document.body.style.overflowY = "auto";
        this.$refs.mobileMenu.classList.remove('active');
      }
    },
    updateLang(update) {
      var pages = {
        "ch": "index.html", 
        "en": "en.html"
      };

      if(update !== this.lang) {
        window.location.href = pages[update];
      }
    }
  }
};
</script>