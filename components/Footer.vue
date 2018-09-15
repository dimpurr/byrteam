<template>
    <div class="root">
        <div class="team">2003 ~ 2018 © 北邮人团队 BYR TEAM</div>
        <div class="team">Design & Code with <span class="love">❤</span></div>
    </div>
</template>
<script>
export default {};
</script>
<style lang="scss" scoped>
$author: jasonwu;
.root {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  .team{
      color:#999;
      .love{
          color:#ff5a79;
      }
  }
}
</style>
