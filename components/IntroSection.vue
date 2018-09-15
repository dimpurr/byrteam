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
        <div class="intro-right">
            <img src="/slide-main-team.png" />
        </div>
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
            "成立于 2003 年 ，来自北邮人论坛、北邮人 BT 和 BYRIO 社区，传统悠久、技术深厚、大佬如云"
        },
        {
          title: "可能是北邮第二值得加入的团队，如今招新。1",
          content:
            "成立于 2003 年 ，来自北邮人论坛、北邮人 BT 和 BYRIO 社区，传统悠久、技术深厚、大佬如云4"
        },
        {
          title: "可能是北邮第二值得加入的团队，如今招新。2",
          content:
            "成立于 2003 年 ，来自北邮人论坛、北邮人 BT 和 BYRIO 社区，传统悠久、技术深厚、大佬如云5"
        },
        {
          title: "可能是北邮第二值得加入的团队，如今招新。3",
          content:
            "成立于 2003 年 ，来自北邮人论坛、北邮人 BT 和 BYRIO 社区，传统悠久、技术深厚、大佬如云6"
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
