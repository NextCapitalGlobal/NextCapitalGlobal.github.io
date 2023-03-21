<template>
  <Nav />
  <!-- main -->
  <div class="main-container">
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
  <News />
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
  <div class="contact-container">
    <div class="inquiry-block clearfix">
      <h3>對 Next Capital 有興趣嗎？</h3>
      <a href="" class="float-right btn-white hidden md:block">聯絡我們</a>
      <p class="mt-5">立即諮詢業務專員</p>
      <a href="" class="btn-white mt-6 inline-block md:hidden">聯絡我們</a>
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
  <Footer />
</template>

<script setup>
import Nav from './components/Ch/Nav.vue'
import Footer from './components/Ch/Footer.vue'
import News from './components/Ch/News.vue'

</script>