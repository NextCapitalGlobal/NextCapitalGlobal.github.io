<template>
  <footer><div class="clearfix">
    <img src="@/assets/logo-white.svg" class="md:float-left logo">
    <ul class="hidden md:inline-block md:float-right">
      <li class="inline-block mr-2.5"><a :href="'mailto:'+email"><img src="@/assets/icon-mail.svg"></a></li>
      <li class="inline-block"><a :href="fb" target="_blank"><img src="@/assets/icon-facebook.svg"></a></li>
    </ul>
    <nav>
      <ul class="my-12 md:my-0 md:text-center">
        <li class="md:inline-block mr-8 mb-10 md:mb-0"><a href="">關於我們</a></li>
        <li class="md:inline-block mr-8 mb-10 md:mb-0"><a href="">最新消息</a></li>
        <li class="md:inline-block"><a href="">聯繫我們</a></li>
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
      email: "contact@nextcapital.global",
      fb: "https://www.facebook.com/NextCapitalGlobal/"
    }
  }
}
</script>