<template>
  <Header :lang=lang :langs=langs :menu=menu :email=email :contact_btn=contact_btn />
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
    <div class="block md:flex md:flex-row md:w-full">
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
    <Slider :news=news :title="'Latest News:'" />
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
  <Footer :menu=menu :email=email :fb=fb />
</template>

<script>
import Header from './components/Header.vue'
import Slider from './components/Slider.vue'
import Footer from './components/Footer.vue'

export default {
  data() {
    return {
      email: "contact@nextcapital.global",
      fb: "https://www.facebook.com/NextCapitalGlobal/",
      langs: [{
        'title': 'Chinese', 
        'value': 'ch'
      },{
        'title': 'English', 
        'value': 'en'
      }],
      lang: 'en',
      menu: [
        {
          'title': 'About Us',
          'value': 'about'
        },
        {
          'title': 'Latest News',
          'value': 'news'
        },
        {
          'title': 'Contact Us',
          'value': 'contact'
        }
      ],
      contact_btn: "Contact Us",
      news: [
        {
          "title": "New users can earn up to NT$486 in rewards for completing credit card transactions or tasks.",
          "date": "Event period: 2022-01-22 to 2022-12-30.",
          "intro": "For new accounts activated during the event period, completing any of the following scenarios by the end of the following month will qualify for a cashback reward of NT$366 …",
          "thumbnail": "",
          "url": ""
        },
        {
          "title": "New users can earn up to NT$486 in rewards for completing credit card transactions or tasks.",
          "date": "Event period: 2022-01-22 to 2022-12-30.",
          "intro": "For new accounts activated during the event period, completing any of the following scenarios by the end of the following month will qualify for a cashback reward of NT$366 …",
          "thumbnail": "",
          "url": ""
        },
        {
          "title": "New users can earn up to NT$486 in rewards for completing credit card transactions or tasks.",
          "date": "Event period: 2022-01-22 to 2022-12-30.",
          "intro": "For new accounts activated during the event period, completing any of the following scenarios by the end of the following month will qualify for a cashback reward of NT$366 …",
          "thumbnail": "",
          "url": ""
        },
        {
          "title": "New users can earn up to NT$486 in rewards for completing credit card transactions or tasks.",
          "date": "Event period: 2022-01-22 to 2022-12-30.",
          "intro": "For new accounts activated during the event period, completing any of the following scenarios by the end of the following month will qualify for a cashback reward of NT$366 …",
          "thumbnail": "",
          "url": ""
        },
        {
          "title": "New users can earn up to NT$486 in rewards for completing credit card transactions or tasks.",
          "date": "Event period: 2022-01-22 to 2022-12-30.",
          "intro": "For new accounts activated during the event period, completing any of the following scenarios by the end of the following month will qualify for a cashback reward of NT$366 …",
          "thumbnail": "",
          "url": ""
        }
      ]
    }
  },
  components: {
    Header,
    Slider,
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