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
    margin-top: -60px

.intro-right
    height: 100%
    .swiper-item
        height: 100%
        width: 100%
        text-align: right
        img
            margin-top: 80px
            margin-right: -30px
            height: 380px
            width: 100%
            object-fit: cover
            border-radius: 70% 30% 70% 30%
    // .swiper-item::before
    //     content: ''
    //     display: block
    //     position: absolute
    //     margin-top: 100px
    //     margin-left: -140px
    //     z-index: 10
    //     height: 330px
    //     width: 200px
    //     background: #fff
    //     // border: 1px solid #ddd
    //     transform: skew(-20deg)
.intro-left
    z-index: 100
    position: relative
    margin-top: 7rem
    width: 23rem
    .title
        font-size: 1.9rem
        // letter-spacing: 5px
        // letter-spacing: 2px
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
