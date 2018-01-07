<template lang="html">
  <div class="menu">
    <h2>Menu</h2>
  </div>
</template>

<script>
export default {
  name: 'Menu'
}
</script>

<style lang="scss" scoped>
  .menu {
    background-color: rgba(0,0,0,0.7);
    height: 100vh;
    position: fixed;
    width: 20vw;
    padding-left: 20px;
    color: white;

    * {
      color: blue;
    }
  }
</style>
