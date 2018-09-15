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
    <section class="intro">
    <swiper class="swiper">
      <swiper-item v-for="(item,$index) in intros" :key="item.title" :show="introCurrentIdx == $index">
        <span class="title">{{item.title}}</span>
        <p>{{item.content}}</p>
      </swiper-item>
    </swiper>
    </section>

    <btn @click="a=false" :flat="true">报名</btn>
  </div>
</template>

<script>

import Swiper from '~/components/Swiper';
import SwiperItem from '~/components/SwiperItem';
import Btn from '~/components/Btn';
export default {
  components: {
    Swiper,SwiperItem,Btn
  },data(){
    return {
      a:true,
      introCurrentIdx:0,
      intros:[
        {title:"可能是北邮第二值得加入的团队，如今招新。",content:"成立于 2003 年 ，来自北邮人论坛、北邮人 BT 和 BYRIO 社区，传统悠久、技术深厚、大佬如云"},
        {title:"可能是北邮第二值得加入的团队，如今招新。1",content:"成立于 2003 年 ，来自北邮人论坛、北邮人 BT 和 BYRIO 社区，传统悠久、技术深厚、大佬如云4"},
        {title:"可能是北邮第二值得加入的团队，如今招新。2",content:"成立于 2003 年 ，来自北邮人论坛、北邮人 BT 和 BYRIO 社区，传统悠久、技术深厚、大佬如云5"},
        {title:"可能是北邮第二值得加入的团队，如今招新。3",content:"成立于 2003 年 ，来自北邮人论坛、北邮人 BT 和 BYRIO 社区，传统悠久、技术深厚、大佬如云6"}
      ]
    }
  }
};
</script>

<style lang="stylus" scoped>
$width-screen = 700px;
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

