<template>
  <div class="error-box">
    <div class="error-font-title">404</div>
    <div class="error-font-content">
      oh no! 您访问的页面<span class="lost">失联</span>了…
    </div>
    <div class="error-menu">
      <el-button @click="goBack">返回上一页</el-button>
      <el-button type="primary" @click="goHome">进入首页</el-button>
    </div>
  </div>
</template>

<script>
  export default {
    name: '404',
    methods: {
      goBack () {
        window.history.length > 1 ? this.$router.go(-1) : this.$router.push('/')
      },
      goHome () {
        this.$router.push('/')
      }
    }
  }
</script>

<style lang="scss">
  .error-box {
    width: 50%;
    height: 50%;
    margin: 0 auto;

    .error-font-title {
      font-size: 10vw;
      color: black;
      font-weight: bold;
    }

    .error-font-content {
      font-size: 3vw;
      color: #dadada;
      font-weight: bold;

      .lost {
        color: lightcoral;
      }
    }

    .error-menu {
      width: 60%;
      display: flex;
      flex-direction: row;
      justify-content: space-around;
      align-content: center;
      margin: 20px auto;
    }
  }
</style>
