<template>
  <div class="header hidden md:block"><div class="inner clearfix">
    <a href="" class="float-left logo"><img src="@/assets/logo.svg"></a>
    <div class="float-right">
      <div class="lang-block inline-block mr-6">
        <img class="inline-block" src="@/assets/icon-lang.svg">
        <select v-model="selected">
          <option v-for="row in langs" v-text="row.title" :value="row.value"></option>
        </select>
      </div>
      <a href="" class="btn-black inline-block">聯繫我們</a>
    </div>
    <nav>
      <ul class="text-center">
        <li class="inline-block mr-8"><a href="">關於我們</a></li>
        <li class="inline-block mr-8"><a href="">最新消息</a></li>
        <li class="inline-block"><a href="">聯繫我們</a></li>
      </ul>
    </nav>
  </div></div>
  <div class="header block md:hidden"><div class="inner clearfix">
    <a href="" class="float-left logo"><img src="@/assets/logo.svg"></a>
    <button class="float-right menu"><img src="@/assets/icon-menu.svg"></button>
  </div></div>
</template>

<script>
export default {
  data() {
    return {
      langs: [{
        'title': '中文', 
        'value': 'ch'
      },{
        'title': '英文', 
        'value': 'en'
      }],
      selected: 'ch'
    }
  },
  watch: {
    selected: (value) => {
      if(value === 'en') {
        //goto en page
        window.location.href = "en.html";
      }
    }
  },
  methods: {

  }
}
</script>