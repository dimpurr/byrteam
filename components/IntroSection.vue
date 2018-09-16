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
            <swiper-arrows :isFirst="this.introCurrentIdx == 0" :isLast=" this.introCurrentIdx == (this.intros.length - 1)" @next="introCurrentIdx++" @prev="introCurrentIdx--" />
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
import SwiperArrows from "~/components/SwiperArrows";
import Btn from "~/components/Btn";
import {intros} from "~/data/intro.json";
export default {
  components: {
    Swiper,
    SwiperItem,
    Btn,
    SwiperArrows
  },
  data() {
    return {
      introCurrentIdx: 0,
      intros
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

</style>
