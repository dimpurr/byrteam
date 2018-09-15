<template>
    <section class="intro">
        <div class="intro-left">
            <swiper>
                <swiper-item v-for="(item,$index) in intros" :key="item.title" :show="introCurrentIdx == $index">
                    <span class="title">{{item.title}}</span>
                    <p>{{item.content}}</p>
                </swiper-item>
            </swiper>
            <div class="btns">
                <btn>立即报名</btn>
                <btn :flat="true">加群咨询</btn>
            </div>
            <div class="arrows">
                <span :class="{visible:isArrowLeftShow,hidden:!isArrowLeftShow}" @click="introCurrentIdx--">&lt;</span>
                <span :class="{visible:isArrowRightShow,hidden:!isArrowRightShow}" @click="introCurrentIdx++">&gt;</span>
            </div>
        </div>

        <swiper class="intro-right">

            <swiper-item v-for="(item,$index) in intros" :key="item.title" :show="introCurrentIdx == $index">
                <img :src="item.imgUrl" />
            </swiper-item>
        </swiper>

    </section>
</template>
<script>
import Swiper from "~/components/Swiper";
import SwiperItem from "~/components/SwiperItem";
import Btn from "~/components/Btn";
export default {
  components: {
    Swiper,
    SwiperItem,
    Btn
  },
  computed: {
    isArrowLeftShow() {
      return this.introCurrentIdx !== 0;
    },
    isArrowRightShow() {
      return this.introCurrentIdx !== this.intros.length - 1;
    }
  },
  data() {
    return {
      introCurrentIdx: 0,
      intros: [
        {
          title: "可能是北邮第二值得加入的团队，如今招新。",
          content:
            "成立于 2003 年 ，来自北邮人论坛、北邮人 BT 和 BYRIO 社区，传统悠久、技术深厚、大佬如云",
          imgUrl: "/slide-main-team.png"
        },
        {
          title: "可能是北邮第二值得加入的团队，如今招新。1",
          content:
            "成立于 2003 年 ，来自北邮人论坛、北邮人 BT 和 BYRIO 社区，传统悠久、技术深厚、大佬如云4",
          imgUrl: "/slide-main-tshirt.png"
        },
        {
          title: "可能是北邮第二值得加入的团队，如今招新。2",
          content:
            "成立于 2003 年 ，来自北邮人论坛、北邮人 BT 和 BYRIO 社区，传统悠久、技术深厚、大佬如云5",
          imgUrl: "/slide-main-team.png"
        },
        {
          title: "可能是北邮第二值得加入的团队，如今招新。3",
          content:
            "成立于 2003 年 ，来自北邮人论坛、北邮人 BT 和 BYRIO 社区，传统悠久、技术深厚、大佬如云6",
          imgUrl: "/slide-main-tshirt.png"
        }
      ]
    };
  }
};
</script>
<style lang="sass" scoped>
.swiper 
    height: 13rem
    width: 110%

.intro 
    display: flex
    flex-flow: row nowrap
    height: 30rem

.intro-right
    height: 100%
    .swiper-item
        height: 100%
        width: 100%
        img
            height: 100%
.intro-left
    margin-top: 7rem
    width: 23rem
    .title
        font-size: 1.9rem
        letter-spacing: 5px
    p
        font-size: 0.9rem
        color: rgb(125, 125, 125)
        padding-top: 5px
        width: 75%

    .btns
        display: flex
        margin-top: 1rem
        flex-flow: row nowrap
    .arrows
        margin-top: 1rem
    .arrows *
        cursor: pointer
        font-size: 1.6rem
        color: rgb(125, 125, 125)
        padding: 0.2rem

.visible 
  visibility: visible
  opacity: 1
  transition: opacity 0.2s linear

.hidden 
  visibility: hidden
  opacity: 0
  transition: visibility 0s 0.2s, opacity 0.2s linear
</style>
