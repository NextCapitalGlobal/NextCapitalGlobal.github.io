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
      <a :href="'mailto:'+email" class="btn-black inline-block">聯繫我們</a>
    </div>
    <nav class="hidden md:block">
      <ul class="menu text-center">
        <li class="inline-block mr-8" @click="goto('about')">關於我們</li>
        <li class="inline-block mr-8" @click="goto('news')">最新消息</li>
        <li class="inline-block" @click="goto('contact')">聯繫我們</li>
      </ul>
    </nav>
    <button class="block md:hidden float-right btn-mobile-menu" @click="toggleMobileMenu('open')"><img src="@/assets/icon-menu.svg"></button>
  </div></div>
  <div class="block md:hidden mobile-menu-container" ref="mobileMenu">
    <button class="block md:hidden float-right btn-mobile-menu" @click="toggleMobileMenu('close')"><img src="@/assets/icon-close.svg"></button>
    <nav>
      <ul class="menu mt-8 mb-8">
        <li class="mb-8" @click="goto('about')">關於我們</li>
        <li class="mb-8" @click="goto('news')">最新消息</li>
        <li @click="goto('contact')">聯繫我們</li>
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
    <h1 class="mb-6">Next Capital<br>推動<p class="highlight">金融科技</p>未來發展</h1>
    <div class="md:w-3/5">
      <p>Next Capital 是一間創業投資公司 (Venture Capital, VC) 投資金融科技 (Financial technology, FinTch）相關有潜力的公司，推動金融科技未來發展，包含支付、P2P借貸、區塊鏈服務、財富管理、保險科技等等的金融服務。</p>
    </div>
  </div>
  <div class="card-container text-center clearfix">
    <img class="float-right hidden md:inline-block" src="@/assets/card-yellow.png">
    <img class="float-none inline-block md:float-right" src="@/assets/card-blue.png">
  </div>
  <div class="feature-container">
    <p class="mb-10 title">安全可靠的 NEXT 協助你</p>
    <div class="block md:flex md:flex-row">
      <div class="basis-1/3 feature-block block md:flex md:flex-nowrap">
        <button class="flex-none icon"><img src="@/assets/icon-money.svg"></button>
        <div>
          <p class="title">擁有你的 MasterCard</p>
          <p>Next Capital 發行 MasterCard 萬事達通信用卡。</p>
        </div>
      </div>
      <div class="basis-1/3 feature-block block md:flex md:flex-nowrap">
        <button class="flex-none icon"><img src="@/assets/icon-pay.svg"></button>
        <div>
          <p class="title">代收代付 X Pay</p>
          <p>X Pay 提供企業合作方案，提供快速收款連結，支援 crypto 代收代付，讓商家也能向消費者收取 crypto。</p>
        </div>
      </div>
      <div class="basis-1/3 feature-block block md:flex md:flex-nowrap">
        <button class="flex-none icon"><img src="@/assets/icon-grow.svg"></button>
        <div>
          <p class="title">數位支票 BitCheck</p>
          <p>為您的跨境貿易與國際支付，提供最安全的免費線上履約保證。</p>
        </div>
      </div>
    </div>
  </div>
  <!-- news -->
  <div class="news-container" ref="news">
    <div class="clearfix mb-8">
      <h3 class="float-left">最新消息</h3>
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
          <p>活動期間<br>{{row.date}}</p>
          <p v-text="row.intro"></p>
        </div>
      </a></div>
    </div>
  </div>
  <!-- intro -->
  <div class="intro-container">
    <h3 class="text-center">擁有你的 <p class="highlight">MasterCard</p></h3>
    <div class="intro-block">
      <div class="cover-block"><img src="@/assets/card-screenshot.svg"></div>
      <div class="content-block">
        <p>新辦用戶享有低手續費率。</p>
        <p>在 Next Capital 集團下使用所有服務，享有額外優惠。</p>
        <a href="" class="btn-black inline-block mt-6">即將上市</a>
      </div>
    </div>
  </div>
  <!-- contact -->
  <div class="contact-container" ref="contact">
    <div class="inquiry-block clearfix">
      <h3>對 Next Capital 有興趣嗎？</h3>
      <a :href="'mailto:'+email" class="float-right btn-white hidden md:block">聯絡我們</a>
      <p class="mt-5">立即諮詢業務專員</p>
      <a :href="'mailto:'+email" class="btn-white mt-6 inline-block md:hidden">聯絡我們</a>
    </div>
    <div class="subscribe-block">
      <h3 class="m-0 mb-8">闞注我們的最新動態</h3>
      <label class="subscribe-form">
        <img src="@/assets/icon-mail-border.svg" class="pointer-events-none icon">
        <input type="email" placeholder="輸入您的信箱" class="md:w-1/2">
        <button class="btn-white hidden md:inline-block">訂閱</button>
      </label>
      <button class="mt-3 btn-white block md:hidden">訂閱</button>
    </div>
  </div>
  <!-- footer -->
  <footer><div class="clearfix">
    <img src="@/assets/logo-white.svg" class="md:float-left logo">
    <ul class="hidden md:inline-block md:float-right">
      <li class="inline-block mr-2.5"><a :href="'mailto:'+email"><img src="@/assets/icon-mail.svg"></a></li>
      <li class="inline-block"><a :href="fb" target="_blank"><img src="@/assets/icon-facebook.svg"></a></li>
    </ul>
    <nav>
      <ul class="my-12 md:my-0 md:text-center">
        <li class="md:inline-block mr-8 mb-10 md:mb-0" @click="goto('about')">關於我們</li>
        <li  class="md:inline-block mr-8 mb-10 md:mb-0" @click="goto('news')">最新消息</li>
        <li class="md:inline-block" @click="goto('contact')">聯繫我們</li>
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
        'title': '中文', 
        'value': 'ch'
      },{
        'title': '英文', 
        'value': 'en'
      }],
      selected: 'ch',
      news: [
        {
          "title": "新戶刷卡或完成任務享最高回饋NT$486",
          "date": "2022-01-22-2022-12-30",
          "intro": "帳戶啟用後次月底前符合以下任一情境，即享現金回饋NT$366 …",
          "thumbnail": "/assets/news-thumb.png",
          "url": ""
        },
        {
          "title": "新戶刷卡或完成任務享最高回饋NT$486",
          "date": "2022-01-22 - 2022-12-30",
          "intro": "帳戶啟用後次月底前符合以下任一情境，即享現金回饋NT$366 …",
          "thumbnail": "/assets/news-thumb.png",
          "url": ""
        },
        {
          "title": "新戶刷卡或完成任務享最高回饋NT$486",
          "date": "2022-01-22 - 2022-12-30",
          "intro": "帳戶啟用後次月底前符合以下任一情境，即享現金回饋NT$366 …",
          "thumbnail": "/assets/news-thumb.png",
          "url": ""
        }
      ]
    }
  },
  mounted() {
    this.detectDevice();
  },
  watch: {
    selected: (value) => {
      if(value === 'en') {
        window.location.href = "en.html";
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