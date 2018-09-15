<template>
    <div class="service">
        <div class="title">
            <div class="slash-box">
                <div class="slash"></div>
                <div class="slash"></div>
            </div>
            <div class="cn">服务</div>
            <div class="en">SERVICES</div>
        </div>
        <div class="item-list">
            <div class="item" v-for="(item,index) in itemList" :key="index">
                <img :src="item.url" />
                <div class="title">{{item.title}}</div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  props: {
    itemList: {
      type: Array,
      default: () => {
        return [
          { url: "services-byrbbs.png", title: "北邮人论坛" },
          { url: "services-byrbt.png", title: "北邮人 BT" },
          { url: "services-iptv.png", title: "北邮人 IPTV" },
          { url: "services-byrio.png", title: "BYRIO开源社区" },
          { url: "services-blogroll.png", title: "北邮人博客圈" },
          { url: "services-yiban.png", title: "易班生活服务" }
        ];
      }
    }
  }
};
</script>

<style lang="scss" scoped>
.service {
  display: flex;
  flex-direction: column;
}
.title {
  position: relative;
  margin-bottom: 1.5rem;
  .slash-box {
      position: absolute;
      display: flex;
      flex-direction: row;
      left:-1rem;
    .slash {
        width: 0.2rem;
        height: 2.7rem;
        background-color: #66ccff;
    }
  }
  .cn {
    font-size: 1.2rem;
    font-weight: 500;
  }
  .en {
    color: #666;
    font-size: 0.8rem;
    font-weight: 500;
  }
}
.item-list {
  display: flex;
  flex-direction: row;
  .item {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 0 1.2rem;
    img {
      width: 2.75rem;
      height: 2.75rem;
      margin: 0.75rem 0;
    }
    .title {
      font-size: 0.8rem;
      color: #333;
    }
  }
}
</style>
