<template>
  <div class="recommend">
    <div class="recommend-title">周末去哪儿</div>
    <ul>
      <li
        class="item border-bottom"
        v-for="item of recommendList"
        :key="item.id"
      >
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" />
        </div>
        <div class="item-info">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-desc">
            {{ item.desc }}
          </p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data() {
    return {
      recommendList: [
        {
          id: '0001',
          imgUrl:
            'https://imgs.qunarzz.com/p/tts9/1611/48/a0aa0ab732239402.jpg_r_480x320x95_8058890b.jpg',
          title: '北京当地游1天跟团游',
          desc: '北京故宫深度半日游｜上午下午2班可选｜纯玩0购物｜全景游'
        },
        {
          id: '0002',
          imgUrl:
            'https://imgs.qunarzz.com/p/tts9/1611/48/a0aa0ab732239402.jpg_r_480x320x95_8058890b.jpg',
          title: '北京当地游1天跟团游',
          desc: '北京故宫深度半日游｜上午下午2班可选｜纯玩0购物｜全景游'
        },
        {
          id: '0003',
          imgUrl:
            'https://imgs.qunarzz.com/p/tts9/1611/48/a0aa0ab732239402.jpg_r_480x320x95_8058890b.jpg',
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
.item-img-wrapper
  overflow hidden
  height 0
  padding-bottom 33.9%
  .item-img
    width 100%
.item-info
  padding 0.1rem
  .item-title
    line-height 0.54rem
    font-size 0.32rem
    ellipsis()
  .item-desc
    line-height 0.4rem
    color #ccc
    ellipsis()
</style>
