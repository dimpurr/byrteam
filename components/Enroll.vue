<template>
  <div class="root">
    <div class="join-us">
      <div class="join-us-cn">加入我们</div>
      <div class="join-us-en">JOIN US</div>
    </div>
    <div class="form">
      <div class="inputs">
        <input class="input" placeholder="姓名" />
        <input class="input" placeholder="手机" />
        <input class="input" placeholder="年级" />
        <input class="input" placeholder="学院" />
      </div>
      <div class="department">
        <span class="title">部门</span>
        <span @click="()=>OnJobClick(index)" class="job" :class="{'job-sel':item.selected}" v-for="(item,index) in jobList" :key="index">{{item.title}}</span>
      </div>
      <button class="enroll" type="button">立即报名</button>
    </div>
  </div>
</template>
<script>
export default {
  methods: {
    OnJobClick(index) {
      this.jobList[index].selected ^= 1;
    }
  },
  props: {
    jobList: {
      type: Array,
      default: () => {
        return [
          { title: "技术组", selected: true },
          { title: "美工组", selected: false },
          { title: "文宣组", selected: true },
          { title: "外联组", selected: false },
          { title: "新媒体组", selected: false }
        ];
      }
    }
  }
};
</script>
<style lang="scss" scoped>
$theme: #66ccff;
$author: jasonwu;
.root {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  .join-us {
    padding: 0.7rem 1rem;
    border: {
      top: 0.3rem solid $theme;
      bottom: 0.3rem solid $theme;
    }
    .join-us-cn {
      font-size: 1.2rem;
    }
    .join-us-en {
      font-size: 1.1rem;
      font-weight: 500;
      color: #666;
    }
  }
  .form {
    margin-top: 3.1rem;
    width: 28rem;
    .inputs {
      width: 100%;
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      .input {
        width: 11.7rem;
        margin: 0.2rem 0;
        height: 3rem;
        line-height: 150%;
        padding-left: 2rem;
        font-size: 13px;
        background-color: #f8f8f8;
        border: none;
        outline: none;
        transition: all 0.25s;
        &:focus{
          background-color: #f3f3f3;
        }
      }
    }
    .department {
      padding: 0.95rem 0;
      .title {
        font-size: 0.85rem;
        margin: 0 1.55rem 0 1.85rem;
        color: #666;
      }
      .job {
        font-size: 13px;
        padding: 0.55rem 0.55rem;
        margin: 0 0.31rem;
        transition: all 0.1s;
      }
      .job:hover {
        cursor: pointer;
      }
      .job-sel {
        background-color: #f8f8f8;
      }
    }
    .enroll {
      border: none;
      background-color: #66ccff;
      width: 100%;
      height: 3rem;
      color: #fff;
      font-size: 0.85rem;
      outline: none;
      transition: all 0.25s;
      &:hover {
        background-color: #5fbbe9;
      }
      &:active {
        background-color: #57acd6;
      }
    }
  }
}
</style>

