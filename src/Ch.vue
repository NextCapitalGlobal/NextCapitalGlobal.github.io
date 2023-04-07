<template>
  <Header :lang=lang :langs=langs :menu=menu :email=email :contact_btn=contact_btn />
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
    <div class="block md:flex md:flex-row md:w-full">
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
        <a class="btn-white hidden md:inline-block" href="mailto:contact@nextcapital.global?subject=NextCapital%20關注最新動態&body=您好，%0A我要關注最新動態～ %0A%0A謝謝">訂閱</a>
      </label>
      <a class="mt-3 btn-white block md:hidden" href="mailto:contact@nextcapital.global?subject=NextCapital%20關注最新動態&body=您好，%0A我要關注最新動態～ %0A%0A謝謝">訂閱</a>
    </div>
  </div>
  <!-- footer -->
  <Footer :menu=menu :email=email :fb=fb />
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'

export default {
  data() {
    return {
      email: "contact@nextcapital.global",
      fb: "https://www.facebook.com/NextCapitalGlobal/",
      langs: [
        {
          'title': '中文', 
          'value': 'ch'
        },
        {
          'title': '英文', 
          'value': 'en'
        }
      ],
      lang: 'ch',
      menu: [
        {
          'title': '關於我們',
          'value': 'about'
        },
        {
          'title': '最新消息',
          'value': 'news'
        },
        {
          'title': '聯繫我們',
          'value': 'contact'
        }
      ],
      contact_btn: "聯繫我們",
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
  components: {
    Header,
    Footer
  },
  methods: {
    goto(selection) {
      const el = this.$refs[selection];
      var offset = document.getElementById('header').clientHeight;
      var elPosition = el.getBoundingClientRect().top;
      var position = elPosition + window.pageYOffset - offset;

      window.scrollTo({
        top: position,
        behavior: 'smooth'
      });
    }
  }
}
</script>