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
import {services} from '~/data/services.json';
export default {
  props: {
    itemList: {
      type: Array,
      default: () => {
        return services;
      }
    }
  }
};
</script>

<style lang="scss" scoped>
$author: jasonwu;
.service {
  display: flex;
  flex-direction: column;
  width: 100%;
}
.title {
  position: relative;
  margin-bottom: 1rem;
  .slash-box {
    position: absolute;
    display: flex;
    flex-direction: row;
    left: -2rem;
    .slash {
      width: 0.3rem;
      height: 2.7rem;
      background-color: #66ccff;
      transform: skew(-20deg);
      margin-left: 0.3rem;
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
  margin-left: -1rem;
  width: 100%;
  justify-content: space-around;
  .item {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 0 1rem;
    img {
      width: 2.75rem;
      height: 2.75rem;
      margin: 0.5rem 0;
    }
    .title {
      font-size: 0.8rem;
      color: #333;
    }
  }
}
</style>
