<template>
	<div class="news-container">
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
</template>

<script>
export default {
  data() {
    return {
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