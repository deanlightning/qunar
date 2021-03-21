<template>
  <div class="home">
    <home-header></home-header>
    <home-swiper :swiperList="swiperList"></home-swiper>
    <home-icons :iconList="iconList"></home-icons>
    <home-recommend :recommendList="recommendList"></home-recommend>
    <home-weekend :weekendList="weekendList"></home-weekend>
  </div>
</template>

<script>
import HomeHeader from '../components/Home/Header'
import HomeSwiper from '../components/Home/Swiper'
import HomeIcons from '../components/Home/Icons'
import HomeRecommend from '../components/Home/Recommend'
import HomeWeekend from '../components/Home/Weekend'
import axios from 'axios'

export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data() {
    return {
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    }
  },
  mounted() {
    this.getHomeInfo()
  },
  methods: {
    getHomeInfo() {
      axios.get('/api/index.json').then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc(res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.recommendList = data.recommendList
        this.weekendList = data.weekendList
      }
    }
  }
}
</script>
