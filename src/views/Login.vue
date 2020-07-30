<template>
  <div class="login-layout">
    <div class="login-box">
      <div class="login-title">
        <div @click="clickLogin(0)" :class="activeIndex === 0 ? 'active' : 'un-active'">扫码登录</div>
        <div @click="clickLogin(1)" :class="activeIndex === 1 ? 'active' : 'un-active'">密码登录</div>
      </div>
      <div v-show="activeIndex === 0" id="qrcode"/>
      <div v-show="activeIndex === 1" class="input-content">
        <el-input placeholder="请输入账号" v-model="account">
          <template slot="prepend">账号</template>
        </el-input>
        <el-input class="input-password" show-password placeholder="请输入密码" v-model="passworrd">
          <template slot="prepend">密码</template>
        </el-input>
        <div class="forget">
          <span>忘记登录密码？</span>
        </div>
        <el-button class="login" type="primary">登录</el-button>
        <div class="forget">
          <a href="https://github.com/dachaodc">免费注册</a>
        </div>
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
        qrcode: {},
        account: '',
        passworrd: ''
      }
    },
    mounted () {
      this.qrcode = document.getElementById('qrcode')
      new QRCode(this.qrcode, {
        text: 'https://github.com/dachaodc',
        width: window.innerWidth * 0.15,
        height: window.innerWidth * 0.15,
        colorDark: '#000000',
        colorLight: '#ffffff'
      })
    },
    methods: {
      clickLogin (type) {
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
      width: 25vw;
      height: 25vw;
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
        width: 15vw;
        height: 15vw;
        text-align: center;
        margin: 10% auto;
      }

      .input-content {
        padding: 25px;

        .input-password {
          margin: 20px 0;
        }

        .forget {
          color: white;
          width: 100%;
          text-align: right;
        }

        .login {
          width: 100%;
          margin: 20px 0;
        }
      }
    }
  }
</style>
