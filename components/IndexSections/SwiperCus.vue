<template>
  <div class="swiper-content">
    <div v-swiper:mySwiper="swiperOption" class="swiperWrap">
      <div class="swiper-wrapper">
        <div v-for="item in list" :key="item.name" class="swiper-slide">
          <div class="customer-item" @click="toCustomer(item.href)">
            <div class="img-box">
              <img :src="item.img" height="66" />
            </div>
            <div class="name">{{ item.name }}</div>
            <div class="desc">
              {{ item.desc }}
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="swiper-button-prev"></div>
    <div class="swiper-button-next"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      list: [
        {
          name: 'UNISWAP',
          desc: 'Uniswap is the first automated market-making transaction protocol built on the Ethereum.',
          href: 'https://uniswap-org.4everland.app/',
          img: require('@/assets/imgs/index/customer/uniswap.png'),
        },
        {
          name: 'DOGECOIN',
          desc: 'Dogecoin is an open source peer-to-peer digital currency,favored by Shiba Inus worldwide.',
          href: 'https://dogecoin.4everland.app/',
          img: require('@/assets/imgs/index/customer/dogecoin.png'),
        },
        {
          name: 'ONTOLOGY',
          desc: 'A blockchain for self-sovereign ID and Data.',
          href: 'https://dweb.ont.io/',
          img: require('@/assets/imgs/index/customer/ontology.png'),
        },
        {
          name: 'HILLSTONE',
          desc: 'Hillstone is a private equity firm founded by experts with more than 10 years of experience in financial institutions.',
          href: 'https://hillstone.finance/',
          img: require('@/assets/imgs/index/customer/hillstone.png'),
        },
        {
          name: 'BELLA',
          desc: 'Bella is a Suite of DeFi Products to make Crypto Banking Simple.',
          href: 'https://dweb.bella.fi/',
          img: require('@/assets/imgs/index/customer/bella.png'),
        },
        {
          name: 'MORE',
          desc: '30,000+ Dapps,including Metaverse,DeFi,GameFi,NFT,etc.',
          href: 'https://4everland.org/firstlanding/dapps',
          img: require('@/assets/imgs/index/customer/more.png'),
        },
      ],
      swiperOption: {
        loop: true,
        autoplay: true,
        slidesPerView: 3,
        centeredSlides: true,
        speed: 2500,
        navigation: {
          prevEl: '.swiper-button-prev',
          nextEl: '.swiper-button-next',
        },
        on: {
          init() {
            if (this.width < 1161) {
              this.params.slidesPerView = 1
              this.update()
            }
          },
          slideChange() {},
          tap() {},
        },
      },
    }
  },
  mounted() {},
  methods: {
    toCustomer(href) {
      window.open(href)
    },
  },
}
</script>
<style lang="scss" scoped>
.customer-item {
  width: 316px;
  height: 378px;
  padding: 50px 40px;
  padding-top: 120px;
  background: linear-gradient(-30deg, #e1f2ff, #fff6f6);
  border-radius: 20px;
  box-sizing: border-box;
  margin: 20px auto;
  cursor: pointer;

  .img-box {
    width: 70px;
    height: 70px;
    display: flex;
    align-items: center;
    margin-bottom: 23px;
  }
  .name {
    font-size: 28px;
    font-weight: bold;
    margin-bottom: 26px;
  }
  .desc {
    font-size: 14px;
    color: #6c7789;
  }
}
.swiper-slide-active {
  .customer-item {
    background: linear-gradient(-30deg, #afddff, #ffe3e3);
  }
}
.swiper-content {
  position: relative;
  width: 100%;
}
.swiper-button-prev,
.swiper-button-next {
  width: 10px;
  height: 18px;
  background-size: 10px 18px;
  position: absolute;
}
</style>
