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
      <a href="" class="btn-black inline-block">Contact Us</a>
    </div>
    <nav>
      <ul class="text-center">
        <li class="inline-block mr-8"><a href="">About Us</a></li>
        <li class="inline-block mr-8"><a href="">Latest News</a></li>
        <li class="inline-block"><a href="">Contact Us</a></li>
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
        'title': 'Chinese', 
        'value': 'ch'
      },{
        'title': 'English', 
        'value': 'en'
      }],
      selected: 'en'
    }
  },
  watch: {
    selected: (value) => {
      if(value === 'ch') {
        //goto ch page
        window.location.href = "index.html";
      }
    }
  },
  methods: {

  }
}
</script>