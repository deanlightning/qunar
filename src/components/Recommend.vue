<template>
  <div class="recommend">
    <div class="recommend-title">热销推荐</div>
    <ul>
      <li
        class="item border-bottom"
        v-for="item of recommendList"
        :key="item.id"
      >
        <img class="item-img" :src="item.imgUrl" />
        <div class="item-info">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-desc">
            {{ item.desc }}
          </p>
          <button class="item-btn">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data() {
    return {
      recommendList: [
        {
          id: '0001',
          imgUrl:
            '//imgs.qunarzz.com/p/p48/201302/28/bc44faa497db0dcf93835fbb.jpg_256x160_0ba13461.jpg',
          title: '北京当地游1天跟团游',
          desc: '北京故宫深度半日游｜上午下午2班可选｜纯玩0购物｜全景游'
        },
        {
          id: '0002',
          imgUrl:
            '//imgs.qunarzz.com/p/p48/201302/28/bc44faa497db0dcf93835fbb.jpg_256x160_0ba13461.jpg',
          title: '北京当地游1天跟团游',
          desc: '北京故宫深度半日游｜上午下午2班可选｜纯玩0购物｜全景游'
        },
        {
          id: '0003',
          imgUrl:
            '//imgs.qunarzz.com/p/p48/201302/28/bc44faa497db0dcf93835fbb.jpg_256x160_0ba13461.jpg',
          title: '北京当地游1天跟团游',
          desc: '北京故宫深度半日游｜上午下午2班可选｜纯玩0购物｜全景游'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~@/assets/style/mixins.styl'

.recommend-title
  line-height 0.8rem
  background #eee
  text-indent 0.2rem
.item
  overflow hidden
  display flex
  height 1.9rem
  .item-img
    width 1.7rem
    height 1.7rem
    padding 0.1rem
  .item-info
    flex 1
    padding 0.1rem
    min-width 0
    .item-title
      line-height 0.54rem
      font-size 0.32rem
      ellipsis()
    .item-desc
      line-height 0.4rem
      color #ccc
      ellipsis()
    .item-btn
      line-height 0.44rem
      margin-top 0.16rem
      background #ff9300
      padding 0 0.2rem
      border-radius 0.06rem
      color #fff
</style>
