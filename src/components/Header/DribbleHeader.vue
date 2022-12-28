<template>
  <div class="dribble-header">
    <div class="header-inner">
      <img class="logo" :src="logo" alt="logo" />
      <span class="sub-title">{{ subTitle }}</span>
      <h2 class="title">{{ title }}</h2>
    </div>
    <div class="header-right">
      <div class="user">
        <img class="avatar" :src="avatar" alt="" />
        <h6 class="user-name">
          <span class="user-greeting">Hey,</span> {{ user }}
        </h6>
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from "vue";
export default defineComponent({
  props: {
    logo: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    subTitle: {
      type: String,
      required: true,
    },
    avatar: {
      type: String,
      required: true,
    },
    user: {
      type: String,
      required: true,
    },
  },
});
</script>

<style lang="scss" scoped>
.dribble-header {
  background-image: url("../../assets/header.png");
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  height: 360px;
  color: white;
  position: relative;
  .header-inner {
    width: 40%;
    height: 100%;
    margin: auto;
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    padding: 0 20px;
    color: white;
    .sub-title {
      color: #767b90;
      font-weight: 300;
      font-size: 18px;
      line-height: 120%;
    }
    .title {
      font-weight: 600;
      font-size: 32px;
      line-height: 120%;
      margin: 0;
      margin-top: 8px;
    }
    .logo {
      margin-bottom: 36px;
      width: 163px;
      height: 40px;
    }
  }
  .header-right {
    cursor: pointer;
    position: fixed;
    right: 32px;
    top: 20px;
    display: flex;
    align-items: center;
    .user {
      display: flex;
      align-items: center;
      justify-content: center;
      .avatar {
        margin-right: 16px;
      }
      .user-name {
        font-weight: 600;
        font-size: 18px;
        line-height: 135%;
        margin: 0;
        .user-greeting {
          font-weight: 300;
          font-size: 18px;
          line-height: 120%;
        }
      }
    }
  }
}
</style>
