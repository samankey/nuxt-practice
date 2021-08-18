<template>
  <div>
    <button @click="login()">Login</button>
    <button @click="join()">JOIN</button>
  </div>
</template>

<script>
export default {
  methods: {
    login() {
      this.$router.push('/login')
    },
    join() {
      this.$router.push('/join')
    },
  },
}
</script>
