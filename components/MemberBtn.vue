<template>
  <div class="btnWrapper">
    <button class="btn">
      <slot></slot>
    </button>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.btnWrapper {
  width: 100%;

  .btn {
    margin-bottom: 20px;
    padding: 10px 20px;
    width: 100%;
    border: none;
    color: #fff;
    background-color: #005adb;
  }

  .findAccount {
    font-size: 12px;

    a:first-child {
      margin-right: 15px;
    }
  }
}
</style>
