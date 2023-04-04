<template>
  <div class="header" ref="header" :class="{'active': isFixed}"><div class="inner clearfix">
    <a href="/" class="float-left logo"><img src="@/assets/logo.svg"></a>

    <div class="hidden md:block float-right">
      <div class="lang-block inline-block mr-6">
        <img class="inline-block" src="@/assets/icon-lang.svg">
        <select v-model="selected">
          <option v-for="row in langs" v-text="row.title" :value="row.value"></option>
        </select>
      </div>
      <a :href="'mailto:'+email" class="btn-black inline-block">Contact Us</a>
    </div>
    <nav class="hidden md:block">
      <ul class="menu text-center">
        <li class="inline-block mr-8" @click="goto('about')">About Us</li>
        <li class="inline-block mr-8" @click="goto('news')">Latest News</li>
        <li class="inline-block" @click="goto('contact')">Contact Us</li>
      </ul>
    </nav>
    <button class="block md:hidden float-right btn-mobile-menu" @click="toggleMobileMenu('open')"><img src="@/assets/icon-menu.svg"></button>
  </div></div>
  <div class="block md:hidden mobile-menu-container" ref="mobileMenu">
    <button class="block md:hidden float-right btn-mobile-menu" @click="toggleMobileMenu('close')"><img src="@/assets/icon-close.svg"></button>
    <nav>
      <ul class="menu mt-8 mb-8">
        <li class="mb-8" @click="goto('about')">About Us</li>
        <li class="mb-8" @click="goto('news')">Latest News</li>
        <li @click="goto('contact')">Contact Us</li>
      </ul>
    </nav>
    <div class="lang-block">
      <img class="inline-block" src="@/assets/icon-lang.svg">
      <select v-model="selected">
        <option v-for="row in langs" v-text="row.title" :value="row.value"></option>
      </select>
    </div>
  </div>
  <!-- main -->
  <div class="main-container" ref="about">
    <p class="mb-2">Next Capital</p>
    <h1 class="mb-6">Next Capital<br>Driving the Future of <p class="highlight">Fintech</p></h1>
    <div class="md:w-3/5">
      <p>Next Capital is a venture capital (VC) firm that invests in promising companies related to financial technology (FinTech) to drive the future development of FinTech. The firm’s investments cover a wide range of financial services, including payments, peer-to-peer lending, blockchain services, wealth management, insurance technology, and more.</p>
    </div>
  </div>
  <div class="card-container text-center clearfix">
    <img class="float-right hidden md:inline-block" src="@/assets/card-yellow.png">
    <img class="float-none inline-block md:float-right" src="@/assets/card-blue.png">
  </div>
  <div class="feature-container">
    <p class="mb-10 title">Secure and reliable NEXT is here to assist you.</p>
    <div class="block md:flex md:flex-row">
      <div class="basis-1/3 feature-block block md:flex md:flex-nowrap">
        <button class="flex-none icon"><img src="@/assets/icon-money.svg"></button>
        <div>
          <p class="title">Having your MasterCard</p>
          <p>Next Capital issues MasterCard credit cards.</p>
        </div>
      </div>
      <div class="basis-1/3 feature-block block md:flex md:flex-nowrap">
        <button class="flex-none icon"><img src="@/assets/icon-pay.svg"></button>
        <div>
          <p class="title">X Pay offers payment collection and disbursement services.</p>
          <p>X Pay offers corporate partnership plans that provide fast payment links and support for crypto payment and collection, allowing merchants to collect crypto payments from consumers.</p>
        </div>
      </div>
      <div class="basis-1/3 feature-block block md:flex md:flex-nowrap">
        <button class="flex-none icon"><img src="@/assets/icon-grow.svg"></button>
        <div>
          <p class="title">Digital Check service - BitCheck.</p>
          <p>We provide the safest free online performance bond for your cross-border trade and international payments.</p>
        </div>
      </div>
    </div>
  </div>
  <div class="news-container" ref="news">
    <div class="clearfix mb-8">
      <h3 class="float-left">Latest News:</h3>
      <div class="float-right hidden md:block">
        <button class="btn-prev"><img src="@/assets/icon-prev.svg"></button>
        <button class="btn-next"><img src="@/assets/icon-next.svg"></button>
      </div>
    </div>
    <div class="block md:flex">
      <div class="basis-1/3 news-block" v-for="row in news"><a :href="row.url" target="_blank">
        <div class="thumb-block"><img src="@/assets/news-thumb.png"></div>
        <div class="content-block">
          <p class="title" v-text="row.title"></p>
          <p>Event period: {{row.date}}</p>
          <p v-text="row.intro"></p>
        </div>
      </a></div>
    </div>
  </div>
  <!-- intro -->
  <div class="intro-container">
    <h3 class="text-center">Having your <p class="highlight">MasterCard</p></h3>
    <div class="intro-block">
      <div class="cover-block"><img src="@/assets/card-screenshot.svg"></div>
      <div class="content-block">
        <p>New users can enjoy a lower service fee rate when applying.</p>
        <p>Under the Next Capital group, users can enjoy additional benefits when using all services.</p>
        <a href="" class="btn-black inline-block mt-6">Coming soon</a>
      </div>
    </div>
  </div>
  <!-- contact -->
  <div class="contact-container" ref="contact">
    <div class="inquiry-block clearfix">
      <h3>Interested in Next Capital?</h3>
      <a :href="'mailto:'+email" class="float-right btn-white hidden md:block">Contact us.</a>
      <p class="mt-5">Consult our business specialist now.</p>
      <a :href="'mailto:'+email" class="btn-white mt-6 inline-block md:hidden">Contact us.</a>
    </div>
    <div class="subscribe-block">
      <h3 class="m-0 mb-8">Stay updated with our latest news and updates.</h3>
      <label class="subscribe-form">
        <img src="@/assets/icon-mail-border.svg" class="pointer-events-none icon">
        <input type="email" placeholder="Enter your email address." class="md:w-1/2">
        <a class="btn-white hidden md:inline-block" href="mailto:contact@nextcapital.global?subject=NextCapital%20subscribe%20the%20latest%20NEWS&body=Hi%20NextCapital%0ASubscribe%20the%20latest%20NEWS%0A%0AThank%20you">Subscribe</a>
      </label>
      <a class="mt-3 btn-white block md:hidden" href="mailto:contact@nextcapital.global?subject=NextCapital%20subscribe%20the%20latest%20NEWS&body=Hi%20NextCapital%0ASubscribe%20the%20latest%20NEWS%0A%0AThank%20you">Subscribe</a>
    </div>
  </div>
  <footer><div class="clearfix">
    <img src="@/assets/logo-white.svg" class="md:float-left logo">
    <ul class="hidden md:inline-block md:float-right">
      <li class="inline-block mr-2.5"><a :href="'mailto:'+email"><img src="@/assets/icon-mail.svg"></a></li>
      <li class="inline-block"><a :href="fb" target="_blank"><img src="@/assets/icon-facebook.svg"></a></li>
    </ul>
    <nav>
      <ul class="my-12 md:my-0 md:text-center">
        <li class="md:inline-block mr-8 mb-10 md:mb-0" @click="goto('about')">About Us</li>
        <li  class="md:inline-block mr-8 mb-10 md:mb-0" @click="goto('news')">Latest News</li>
        <li class="md:inline-block" @click="goto('contact')">Contact Us</li>
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
  data() {
    return {
      isFixed: false,
      device: "desktop",
      email: "contact@nextcapital.global",
      fb: "https://www.facebook.com/NextCapitalGlobal/",
      langs: [{
        'title': 'Chinese', 
        'value': 'ch'
      },{
        'title': 'English', 
        'value': 'en'
      }],
      selected: 'en',
      news: [
        {
          "title": "New users can earn up to NT$486 in rewards for completing credit card transactions or tasks.",
          "date": "2022-01-22 to 2022-12-30.",
          "intro": "For new accounts activated during the event period, completing any of the following scenarios by the end of the following month will qualify for a cashback reward of NT$366 …",
          "thumbnail": "",
          "url": ""
        },
        {
          "title": "New users can earn up to NT$486 in rewards for completing credit card transactions or tasks.",
          "date": "2022-01-22 to 2022-12-30.",
          "intro": "For new accounts activated during the event period, completing any of the following scenarios by the end of the following month will qualify for a cashback reward of NT$366 …",
          "thumbnail": "",
          "url": ""
        },
        {
          "title": "New users can earn up to NT$486 in rewards for completing credit card transactions or tasks.",
          "date": "2022-01-22 to 2022-12-30.",
          "intro": "For new accounts activated during the event period, completing any of the following scenarios by the end of the following month will qualify for a cashback reward of NT$366 …",
          "thumbnail": "",
          "url": ""
        },
      ]
    }
  },
  mounted() {
    this.detectDevice();
  },
  watch: {
    selected: (value) => {
      if(value === 'ch') {
        //goto ch page
        window.location.href = "index.html";
      }
    }
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
    goto(selection) {
      if(this.device === 'mobile') {
        //close menu
        this.toggleMobileMenu('close');
      }

      const el = this.$refs[selection];
      var offset = this.$refs.header.clientHeight;

      var elPosition = el.getBoundingClientRect().top;
      var position = elPosition + window.pageYOffset - offset;

      window.scrollTo({
        top: position,
        behavior: 'smooth'
      });
    },
    toggleMobileMenu(type) {
      if(type === 'open') {
        document.body.style.overflowY = "hidden";
        this.$refs.mobileMenu.classList.add('active');
      } else {
        document.body.style.overflowY = "auto";
        this.$refs.mobileMenu.classList.remove('active');
      }
    }
  }
}
</script>