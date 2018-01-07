<template>
  <div class="viewer" v-if="colors">
    <Swatch v-for="color in colors" :color="color" :key="color.id" @detailView="showDetail"/>
  </div>
  <div class="viewer" v-else>
    <h2>Loading...</h2>
  </div>
</template>


<script>
import Swatch from './Swatch'

export default {
  name: 'Viewer',
  components: {
    Swatch
  },
  props: ['colors'],
  methods: {
    showDetail (data) {
      this.$emit('showDetail', data)
    }
  }
}
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.viewer {
  position: absolute;
  left: 20vw;
  min-height: 100vh;
  width: 80vw;
  background-color: cornsilk;
  font-size: 0;
  text-align: left;
  /*padding-top: 20px;*/

  h2 {
    font-size: 60px;
    text-align: center;
  }
}
</style>
