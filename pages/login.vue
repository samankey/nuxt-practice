<template>
  <div class="login">
    <div class="loginWrapper">
      <MemberTab />
      <div class="img">
        <img src="../assets/images/man.png" alt="login" />
      </div>
      <div class="loginFormWrapper">
        <form class="loginForm">
          <input
            class="inputId"
            type="text"
            placeholder="아이디를 입력해주세요"
          />
          <input
            class="inputPw"
            type="password"
            placeholder="비밀번호를 입력해주세요"
          />
          <MemberBtn @click.native="loginAlert">로그인</MemberBtn>
        </form>
      </div>
      <div class="findAccount">
        <Nuxt-link to="#">아이디 찾기</Nuxt-link>
        <Nuxt-link to="#">비밀번호 찾기</Nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
import MemberTab from '../components/MemberTab'
import MemberBtn from '../components/MemberBtn'

export default {
  components: {
    MemberTab,
    MemberBtn,
  },

  methods: {
    loginAlert() {
      alert('로그인 되었습니다!')
    },
  },
}
</script>

<style lang="scss" scoped>
.login {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 90vh;

  .loginWrapper {
    width: 300px;
    height: 400px;
    text-align: center;
    background-color: #fff;
    border-radius: 20px;
    box-shadow: 0px 0px 5px #fff;

    .img {
      margin: 15px;
    }

    .loginFormWrapper {
      display: flex;
      justify-content: center;

      .loginForm {
        display: flex;
        flex-direction: column;
        align-items: center;

        input {
          margin-bottom: 10px;
          padding: 10px 20px;
          border: none;
          background-color: rgb(255, 253, 247);

          &:first-child {
            margin-top: 20px;
          }
        }
      }
    }

    .findAccount {
      font-size: 12px;

      a:first-child {
        margin-right: 15px;
      }
    }
  }
}
</style>
