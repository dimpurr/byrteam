<template>
    <div class="root">
        <div class="join-us">
            <div class="join-us-cn">加入我们</div>
            <div class="join-us-en">JOIN US</div>
        </div>
        <div class="form">
            <div class="inputs"><input class="input" placeholder="姓名" />
                <input class="input" placeholder="手机" />
                <input class="input" placeholder="年级" />
                <input class="input" placeholder="学院" /></div>
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
  methods:{
    OnJobClick(index){
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
  width: 40rem;
  border: 1px solid #efefef;
  .join-us {
    padding: 0.75rem 1rem;
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
    margin-top: 3rem;
    width: 73%;
    .inputs {
      width: 100%;
      .input {
        width: 48%;
        height: 3rem;
        line-height: 150%;
        margin: 1% 0;
        padding-left: 2rem;
        font-size: 0.75rem;
        background-color: #f8f8f8;
        border: none;
        outline: none;
      }
      .input:nth-child(odd) {
        margin-right: 1.3%;
      }
      .input:nth-child(even) {
        margin-left: 1.3%;
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
        font-size: 0.85rem;
        padding: 0.45rem 0.45rem;
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
      transition: all 0.5s;
      &:hover {
        filter: brightness(0.96);
      }
      &:active {
        filter: brightness(0.9);
      }
    }
  }
}
</style>

