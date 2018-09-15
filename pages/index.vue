<template>
<div>
  <div class="page">
    <section class="header">
      <a href="/" class="logo">
        <img src="logo.png" />
      </a>
      <nav class="nav">
        <ul>
          <li><a href="#">导航链接</a></li>
          <li><a href="#">导航链接</a></li>
        </ul>
      </nav>
    </section>
    <GroupsIntro />
  </div>
  <FooterArticle />
</div>
</template>

<script>
import AppLogo from '~/components/AppLogo.vue'
import FooterArticle from '~/components/FooterArticle.vue'
import GroupsIntro from '~/components/GroupsIntro.vue'

export default {
  components: {
    AppLogo,
    FooterArticle,
    GroupsIntro
  }
}
</script>

<style lang="stylus" scoped>

$width-screen = 700px

$color-grey-middle = #7d7d7d

a-clear()
  text-decoration none

ul-clear()
  padding 0

li-clear()
  display inline-block

.page
  max-width $width-screen
  margin 0 auto
  font-size 14px

.header
  display flex
  flex-direction row
  margin-top 20px
  a.logo
    img
      height 40px
  .nav
    flex-grow 1
    ul-clear()
    text-align right
    line-height 40px
    li
      li-clear()
      margin-left 20px
      a
        a-clear()
        color $color-grey-middle
</style>

