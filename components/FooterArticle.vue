<template>
    <section class="footerArticle">
      <center><small style="color: #777">或者阅读更多 ...</small></center>
      <ul>
        <li class="article" v-for="(article,index) in articles" :key="index" v-bind:style="{ backgroundImage: `url('${article.img}')` }">
          <a :href="article.url">
            <h3>{{ article.title }}</h3>
            <h4>{{ article.desc }}</h4>
          </a>
        </li>
     </ul>
    </section>
</template>


<script>
export default {
  props: {
    articles: {
      type: Array,
      default: () => {
        return [
          {
            title: '北邮人博客圈',
            desc: '一个汇聚了北邮人学长们优秀博客的地方',
            url: 'http://planet.byr.moe/',
            img: 'article/byrplanet.png'
          },
          {
            title: '北邮人 BYRIO 小分队从重庆 SOSCON 18 学生开源年会胜利归来',
            desc: 'BYRIO 媒体',
            url: 'SOSCON 18 演讲：为了创意者——开源社区与精神的拓展和延续',
            img: 'article/soscon.png'
          },
          {
            title: '北邮 2018 考研专刊（上册）正式发布',
            desc: '北邮人论坛 考研专板',
            url: 'https://bbs.byr.cn/#!article/AimGraduate/1124437',
            img: 'article/AimGraduate.png'
          },
          {
            title: '北邮飞跃手册 留学指南',
            desc: '北邮人论坛 飞跃重洋板块',
            url: 'https://bbs.byr.cn/#!article/GoAbroad/359918',
            img: 'article/GoAbroad.png'
          },
        ];
      }
    }
  }
};
</script>

<style lang="stylus" scoped>
.footerArticle
  margin 50px 0 0 0
  ul
    margin 0
    margin-top 25px
    padding 0
    display flex
    flex-direction row
    flex-wrap wrap
    li
      display flexbox
      width 50%
      position relative
      background-size cover
      list-style none
      &::before
        content ''
        display block
        width 100%
        height 200px
        position absolute
        top 0
        left 0
        background rgba(0,0,0,0.5)
        transition all linear 0.05s
      &:hover::before
        background rgba(0,0,0,0.3)
      a
        display flex
        text-align center
        flex-direction column
        justify-content center
        height 200px
        text-decoration none
        color #FFF
        position relative
        z-index 1
        h3, h4
          // position relative
          // z-index 1
        h4
          font-weight normal
        
</style>
