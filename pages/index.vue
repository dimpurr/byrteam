<template>
  <div class="page">
    <section class="header">
      <a href="/" class="logo">
        <img src="logo.png" />
      </a>
      <nav class="nav">
        <ul>
          <li>
            <a href="#">导航链接</a>
          </li>
          <li>
            <a href="#">导航链接</a>
          </li>
        </ul>
      </nav>
    </section>
   
    <intro-section />
    <btn @click="a=false" :flat="true">报名</btn>
  </div>
</template>

<script>

import Swiper from '~/components/Swiper';
import SwiperItem from '~/components/SwiperItem';
import Btn from '~/components/Btn';
import IntroSection from '~/components/IntroSection.vue';
export default {
  components: {
    Swiper,SwiperItem,Btn,IntroSection
  },data(){
    return {
      a:true
    }
  }
};
</script>

<style lang="stylus" scoped>
$width-screen = 900px;
$color-grey-middle = #7d7d7d;

a-clear() {
  text-decoration: none;
}

ul-clear() {
  padding: 0;
}

li-clear() {
  display: inline-block;
}

.page {
  max-width: $width-screen;
  margin: 0 auto;
  font-size: 14px;
}

.header {
  display: flex;
  flex-direction: row;
  margin-top: 20px;

  a.logo {
    img {
      height: 40px;
    }
  }

  .nav {
    flex-grow: 1;
    ul-clear();
    text-align: right;
    line-height: 40px;

    li {
      li-clear();
      margin-left: 20px;

      a {
        a-clear();
        color: $color-grey-middle;
      }
    }
  }
}

section.intro
  .swiper
    width: 200px
    height: 200px
</style>

