<template lang="html">
  <div class="swatch" :style="{backgroundColor: this.color.hashcode}" @click="clickHandle">
    <h5>{{color.name}}</h5>
  </div>
</template>

<script>
export default {
  name: 'Swatch',
  props: ['color'],
  created () {
    console.log(this.color)
  },
  methods: {
    clickHandle () {
      this.$emit('detailView', this.color)
    }
  }
}
</script>

<style lang="scss">

.swatch {
  height: 10vw;
  width: 10vw;
  display: inline-block;
  border: 1px solid rgba(255,255,255,0.4);
  color: transparent;
  font-size: 20px;
  line-height: 10vw;
  transition: all 0.6s;
  vertical-align: top;
  position: relative;
  text-align: center;
  opacity: 1;
  animation: fadeIn 1s linear 0s 1;

  &:hover {
    color: rgba(255,255,255,0.9);
    cursor: pointer;
    transform: scale(1.2) translateY(5px);
    z-index: 2;
    text-shadow: 0 0 3px black;
  }

  &:before {
    box-shadow: 0 0 5px 1px black;
    content: '';
    opacity: 0;
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
    transition: all 1s;
    z-index: 2;
  }

  &:hover:before {
    opacity: 1;
  }
}


</style>
