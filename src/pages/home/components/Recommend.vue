<template>
  <div>
    <div class="recommend-title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <img class="item-img" :src="item.imgUrl" />
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <p class="item-price"></p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [
        {
          id: '0001',
          imgUrl: 'https://imgs.qunarzz.com/sight/p0/201301/07/d40895cabac2af8a93835fbb.jpg_200x200_adf9e4d2.jpg',
          title: '莫干山',
          desc: '7291条评论'
        },
        {
          id: '0002',
          imgUrl: 'https://imgs.qunarzz.com/sight/p0/201301/07/d40895cabac2af8a93835fbb.jpg_200x200_adf9e4d2.jpg',
          title: '莫干山',
          desc: '7291条评论'
        },
        {
          id: '0003',
          imgUrl: 'https://imgs.qunarzz.com/sight/p0/201301/07/d40895cabac2af8a93835fbb.jpg_200x200_adf9e4d2.jpg',
          title: '莫干山',
          desc: '7291条评论'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .recommend-title
    line-height: .6rem
    background: #eee
    text-indent: .2rem
  .item
    display: flex
    overflow: hidden
    .item-img
      width: 2rem
      height: 2rem
      padding: .1rem
    .item-info
      flex:1
      padding: .1rem
      min-width: 0
      .item-title
        margin-top: .26rem
        line-height: .44rem
        font-size: .32rem
        ellipsis()
      .item-desc
        line-height: .4rem
        color: #ccc
        ellipsis()
      .item-button
        background: #ff9300
        padding: 0 .2rem
        border-radius: .06rem
        color: #fff
        margin-top: .16rem
</style>
