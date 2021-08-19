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
            v-for="{ id, className, type, placeholder } in inputProps"
            :key="id"
            :class="className"
            :type="type"
            :placeholder="placeholder"
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
import axios from 'axios'
import MemberTab from '../components/MemberTab'
import MemberBtn from '../components/MemberBtn'

export default {
  components: {
    MemberTab,
    MemberBtn,
  },

  data() {
    return {
      inputs: [],
    }
  },

  computed: {
    inputProps() {
      return this.inputs.map((input, index) => ({
        id: index,
        className: input.class,
        type: input.type,
        placeholder: input.placeholder,
      }))
    },
  },

  created() {
    axios
      .get('/data/loginInputData.json')
      .then((res) => res.data)
      .then((data) => {
        this.inputs = data.inputs
      })
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
