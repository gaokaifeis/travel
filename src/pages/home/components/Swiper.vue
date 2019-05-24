<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide :key="item.id" v-for="item of swiperList">
        <img class="swiper-img" :src="item.imgUrl" />
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/b1847cf91a34cf95402240a3f62aad77.jpg_750x200_26ea3527.jpg'
      }, {
        id: '0002',
        imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20195/e04c2402fe2fd34f5023b5ad1e54b19c.jpg_750x200_01820f3d.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff !important
  .wrapper
    width: 100%
    height:0
    overflow: hidden
    padding-bottom: 26.7%
    background: #eee
    .swiper-img
      width : 100%
</style>
