<template>
  <div class="detail">
    <detail-banner
      :sightName="sightName"
      :bannerImg="bannerImg"
      :gallaryImgs="gallaryImgs"
    ></detail-banner>
    <detail-header></detail-header>
    <div class="content">
      <detail-list :priceType="priceType"></detail-list>
    </div>
  </div>
</template>

<script>
import DetailBanner from '../components/Detail/Banner'
import DetailHeader from '../components/Detail/Header'
import DetailList from '../components/Detail/List'
import axios from 'axios'

export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data() {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImgs: [],
      priceType: [],
      detailId: 0
    }
  },
  mounted() {
    this.getDetailInfo()
  },
  methods: {
    getDetailInfo() {
      axios
        .get('../../public/mock/detail.json', {
          params: {
            id: this.$route.params.id
          }
        })
        .then(this.getDetailInfoSucc)
    },
    getDetailInfoSucc(res) {
      this.detailId = Number(this.$route.params.id) - 1
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.sightName = data[this.detailId].sightName
        this.bannerImg = data[this.detailId].bannerImg
        this.gallaryImgs = data[this.detailId].gallaryImgs
        this.priceType = data[this.detailId].priceType
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
.content
  height 50rem
</style>
