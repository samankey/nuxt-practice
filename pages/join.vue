<template>
  <div class="join">
    <div class="loginWrapper">
      <MemberTab />
      <div class="loginFormWrapper">
        <form class="loginForm">
          <input
            class="inputId"
            type="text"
            placeholder="이메일을 입력해주세요"
          />
          <input
            class="inputPw"
            type="password"
            placeholder="비밀번호를 입력해주세요"
          />
          <input
            class="inputPw"
            type="password"
            placeholder="비밀번호를 다시 입력해주세요"
          />
          <div class="checkBox">
            <input type="checkbox" name="personalInfo" />
            <label for="personalInfo">개인정보 제공에 동의합니다</label>
          </div>
          <MemberBtn @click.native="joinAlert">회원가입</MemberBtn>
        </form>
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
    joinAlert() {
      alert('회원가입을 축하드립니다!')
    },
  },
}
</script>

<style lang="scss" scoped>
.join {
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

      .checkBox {
        margin-bottom: 10px;
        font-size: 13px;
      }
    }
  }
}
</style>
