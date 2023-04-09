<template>
  <Header :lang=lang :langs=langs :menu=menu :email=email :contact_btn=contact_btn />
  <!-- main -->
  <div class="main-container" ref="about">
    <Intro :content=intro />
  </div>
  <div class="card-container text-center clearfix">
    <img class="float-right hidden md:inline-block" src="@/assets/card-yellow.png">
    <img class="float-none inline-block md:float-right" src="@/assets/card-blue.png">
  </div>
  <div class="feature-container">
    <Feature :feature=feature />
  </div>
  <!-- news -->
  <div class="news-container" ref="news">
    <Slider :news=news />
  </div>
  <!-- intro -->
  <div class="intro-container">
    <Card :card=card />
  </div>
  <!-- contact -->
  <div class="contact-container" ref="contact">
    <Contact :inquiry=inquiry :subscribe=subscribe :email=email />
  </div>
  <!-- footer -->
  <Footer :menu=menu :email=email :fb=fb />
</template>

<script>
import Header from './components/Header.vue'
import Intro from './components/Intro.vue'
import Slider from './components/Slider.vue'
import Feature from './components/Feature.vue'
import Contact from './components/Contact.vue'
import Card from './components/Card.vue'
import Footer from './components/Footer.vue'

function imageUrl(image) {
  return new URL(`./assets/${image}`, import.meta.url).href;
}

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
      intro: {
        name: "Next Capital",
        title: "Next Capital<br>推動<p class='highlight'>金融科技</p>未來發展",
        desc: "Next Capital 是一間創業投資公司 (Venture Capital, VC) 投資金融科技 (Financial technology, FinTch）相關有潜力的公司，推動金融科技未來發展，包含支付、P2P借貸、區塊鏈服務、財富管理、保險科技等等的金融服務。"
      },
      feature: {
        title: "安全可靠的 NEXT 協助你",
        list: [
          {
            title: "擁有你的 MasterCard",
            desc: "Next Capital 發行 MasterCard 萬事達通信用卡。",
            icon: imageUrl("icon-money.svg")
          },
          {
            title: "代收代付 X Pay",
            desc: "X Pay 提供企業合作方案，提供快速收款連結，支援 crypto 代收代付，讓商家也能向消費者收取 crypto。",
            icon: imageUrl("icon-pay.svg")
          },
          {
            title: "數位支票 BitCheck",
            desc: "為您的跨境貿易與國際支付，提供最安全的免費線上履約保證。",
            icon: imageUrl("icon-grow.svg")
          }
        ]
      },
      news: {
        title: "最新消息",
        content: [
          {
            "title": "新戶刷卡或完成任務享最高回饋NT$486",
            "date": "活動期間<br>2022-01-22-2022-12-30",
            "intro": "帳戶啟用後次月底前符合以下任一情境，即享現金回饋NT$366 …",
            "thumbnail": imageUrl("news-thumb.png"),
            "url": ""
          },
          {
            "title": "新戶刷卡或完成任務享最高回饋NT$486",
            "date": "活動期間<br>2022-01-22 - 2022-12-30",
            "intro": "帳戶啟用後次月底前符合以下任一情境，即享現金回饋NT$366 …",
            "thumbnail": imageUrl("news-thumb.png"),
            "url": ""
          },
          {
            "title": "新戶刷卡或完成任務享最高回饋NT$486",
            "date": "活動期間<br>2022-01-22 - 2022-12-30",
            "intro": "帳戶啟用後次月底前符合以下任一情境，即享現金回饋NT$366 …",
            "thumbnail": imageUrl("news-thumb.png"),
            "url": ""
          },
          {
            "title": "新戶刷卡或完成任務享最高回饋NT$486",
            "date": "活動期間<br>2022-01-22 - 2022-12-30",
            "intro": "帳戶啟用後次月底前符合以下任一情境，即享現金回饋NT$366 …",
            "thumbnail": imageUrl("news-thumb.png"),
            "url": ""
          },
          {
            "title": "新戶刷卡或完成任務享最高回饋NT$486",
            "date": "活動期間<br>2022-01-22 - 2022-12-30",
            "intro": "帳戶啟用後次月底前符合以下任一情境，即享現金回饋NT$366 …",
            "thumbnail": imageUrl("news-thumb.png"),
            "url": ""
          }
        ]
      },
      card: {
        title: "擁有你的 <p class='highlight'>MasterCard</p>",
        desc: [
          '新辦用戶享有低手續費率。',
          '在 Next Capital 集團下使用所有服務，享有額外優惠。',
        ],
        btn: '即將上市'
      },
      inquiry: {
        title: "對 Next Capital 有興趣嗎？",
        intro: "立即諮詢業務專員",
        btn: "聯絡我們"
      },
      subscribe: {
        title: "闞注我們的最新動態",
        email_default_msg: "輸入您的信箱",
        link: "mailto:contact@nextcapital.global?subject=NextCapital%20關注最新動態&body=您好，%0A我要關注最新動態～ %0A%0A謝謝",
        btn: "訂閱"
      }
    }
  },
  components: {
    Header,
    Intro,
    Slider,
    Feature,
    Card,
    Contact,
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