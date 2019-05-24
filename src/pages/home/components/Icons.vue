<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" :key="item.id" v-for="item of page">
          <div class="icon-img">
            <img class="icon-imge-content" :src="item.imgUrl" />
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination'
      },
      iconList: [
        {
          id: '0001',
          imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          desc: '景点门票'
        },
        {
          id: '0002',
          imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
          desc: '一日游'
        },
        {
          id: '0003',
          imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
          desc: '百草原'
        },
        {
          id: '0004',
          imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/47/c2b659e048b11602.png',
          desc: '主题乐园'
        },
        {
          id: '0005',
          imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
          desc: '湖州必游'
        },
        {
          id: '0006',
          imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/b1/528a9e80403b8c02.png',
          desc: 'Kitty乐园'
        },
        {
          id: '0007',
          imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/97/02f5043b51b2102.png',
          desc: '莫干山'
        },
        {
          id: '0008',
          imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/67/9a1678221b8e0e02.png',
          desc: '南浔古镇'
        },
        {
          id: '0009',
          imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/a40ee278d67000f2a29d2e20f6a029b3.png',
          desc: '自然风光'
        }
      ]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons >>> .swiper-container
    height: 0
    padding-bottom: 50%
  .icons
    margin-top: .1rem
    .icon
      overflow: hidden
      position: relative
      height: 0
      width: 25%
      float: left
      padding-bottom: 22%
      .icon-img
        position: absolute
        top: 0
        left: 0
        right: 0
        bottom: .44rem
        box-sizing: border-box
        padding: .1rem
        .icon-imge-content
          height: 100%
          display: block
          margin: 0 auto
      .icon-desc
        position: absolute
        left: 0
        right: 0
        bottom: 0
        line-height: .44rem
        height: .44rem
        color: $darkTextColor
        text-align: center
        ellipsis()
</style>
