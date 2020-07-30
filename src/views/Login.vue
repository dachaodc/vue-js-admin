<template>
  <div class="login-layout">
    <div class="login-box">
      <div class="login-title">
        <div @click="clickLogin(0)" :class="activeIndex === 0 ? 'active' : 'un-active'">扫码登录</div>
        <div @click="clickLogin(1)" :class="activeIndex === 1 ? 'active' : 'un-active'">密码登录</div>
      </div>
      <div v-if="activeIndex === 0" id="qrcode"/>
      <div v-else>
        密码登录
      </div>
    </div>
  </div>
</template>

<script>

  import QRCode from 'qrcodejs2'

  export default {
    name: 'Login',
    data () {
      return {
        activeIndex: 0,   // 选择登陆 索引
        qrcode: {}
      }
    },
    mounted () {
      this.qrcode = document.getElementById('qrcode')
      new QRCode(this.qrcode, {
        text: 'https://github.com/dachaodc',
        width: 128,
        height: 128,
        colorDark: '#000000',
        colorLight: '#ffffff'
      })
    },
    methods: {
      clickLogin (type) {
        if (type === 0) {
          new QRCode(this.qrcode, {
            text: 'https://github.com/dachaodc',
            width: 128,
            height: 128,
            colorDark: '#000000',
            colorLight: '#ffffff'
          })
        }
        this.activeIndex = type
      }
    }
  }
</script>

<style lang="scss">

  .login-layout {
    width: 100%;
    height: 100%;

    background: linear-gradient(91deg, #f1eefc, #9dc6ff 70%, #a5bcff);
    /*background: linear-gradient(to right,
     #bb313e25, #bb313e25, #d7222925,
      #dd4a1625, #e4761525, #f5c50025, #f0e92725,
       #b1ce2425, #48a93525, #03944525, #157c4f25,
        #176a5825, #1b556325, #1d386f25, #1d386f25,
         #20277825, #52266325, #8a244b25);*/

    .login-box {
      width: 30vw;
      height: 30vw;
      background: rgba(0, 0, 0, 0.1);
      position: absolute;
      top: 15%;
      left: 50%;
      transform: translateX(-50%);
      border-radius: 10px;

      .login-title {
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        align-content: center;

        .un-active {
          width: 50%;
          font-size: 16px;
          color: white;
          padding: 15px;
        }

        .active {
          width: 50%;
          font-size: 16px;
          color: #0AE;
          padding: 15px;
          border-bottom: 1px solid #0AE;
        }
      }

      #qrcode {
        width: 130px;
        height: 130px;
      }
    }
  }
</style>
