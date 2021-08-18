<template>
  <div class="memberRoute">
    <div>
      <Nuxt-link class="memberLink" to="/login">LOGIN</Nuxt-link>
    </div>
    <div>
      <Nuxt-link class="memberLink" to="/join">JOIN</Nuxt-link>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.memberRoute {
  display: flex;
  justify-content: center;
  margin: 50px 0 30px;

  div:first-child {
    border-right: 2px solid #eee;
  }

  .memberLink {
    padding: 0 40px;
    font: {
      size: 16px;
      weight: 700;
    }
    color: #111;
  }
}
</style>
