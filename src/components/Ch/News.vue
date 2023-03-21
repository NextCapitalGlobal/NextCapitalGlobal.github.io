<template>
	<div class="news-container">
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
</template>

<script>
export default {
  data() {
    return {
      news: [
      	{
      		"title": "新戶刷卡或完成任務享最高回饋NT$486",
      		"date": "2022-01-22-2022-12-30",
      		"intro": "帳戶啟用後次月底前符合以下任一情境，即享現金回饋NT$366 …",
      		"thumbnail": "",
      		"url": ""
      	},
      	{
      		"title": "新戶刷卡或完成任務享最高回饋NT$486",
      		"date": "2022-01-22 - 2022-12-30",
      		"intro": "帳戶啟用後次月底前符合以下任一情境，即享現金回饋NT$366 …",
      		"thumbnail": "",
      		"url": ""
      	},
      	{
      		"title": "新戶刷卡或完成任務享最高回饋NT$486",
      		"date": "2022-01-22 - 2022-12-30",
      		"intro": "帳戶啟用後次月底前符合以下任一情境，即享現金回饋NT$366 …",
      		"thumbnail": "",
      		"url": ""
      	}
      ]
    }
  },
  watch: {
    selected: (value) => {
      console.log(value);
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