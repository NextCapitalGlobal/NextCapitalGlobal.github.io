<template>
  <p class="mb-10 title" v-text="feature.title"></p>
  <div class="block md:flex md:flex-row md:w-full">
    <!-- <div class="basis-1/3 feature-block block md:flex md:flex-nowrap">
      <button class="flex-none icon"><img src="@/assets/icon-money.svg"></button>
      <div>
        <p class="title">擁有你的 MasterCard</p>
        <p>Next Capital 發行 MasterCard 萬事達通信用卡。</p>
      </div>
    </div> -->
    <div v-for="row in feature.list" class="basis-1/3 feature-block block md:flex md:flex-nowrap">
      <button class="flex-none icon"><img :src="row.icon"></button>
      <div>
        <p class="title" v-text="row.title"></p>
        <p v-text="row.desc"></p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Feature",
  props: { 
    feature: Object
  },
  data() {
    return {}
  },
  methods: {
  }
};
</script>