<template lang="html">
  <div class="detail-viewer-container">
    <div class="detail-viewer">
      <div class="close-detail" @click="close" >X</div>
      <div class="detail-banner" :style="{backgroundColor: color.hashcode}" >
        <h4> {{color.name}} </h4>
      </div>
      <h5>Color Codes</h5>
      <h6>{{color.hashcode}}</h6>
      <h6>{{color.rgbcode}}</h6>
      <h5>Description</h5>
      <p>{{color.description}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Detail',
  props: ['color'],
  methods: {
    close () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="scss">
.detail-viewer-container {
  position: absolute;
  background-color: rgba(0,0,0,0.6);
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  z-index: 2;
}

.detail-viewer {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  height: 600px;
  width: 400px;
  font-size: 20px;
  background-color: white;
  z-index: 4;
  text-align: center;
  animation: fadeIn 0.6s ease-in-out 0s 1;

  h5 {
    margin: 10px 0;
  }
  h6 {
    display: inline-block;
    width: 49%;
  }
  p {
    font-size: 14px;
    padding: 0 10px;
  }
}

.detail-banner {
  height: 400px;
  width: 100%;
  color: white;
  text-shadow: 0 0 8px 0 black;
  line-height: 400px;
}

.close-detail {
  position: fixed;
  top: 5px;
  right: 5px;
  font-size: 30px;
  color: white;
  cursor: pointer;
  z-index: 5;
  height: 40px;
  line-height: 40px;
  width: 40px;
  border-radius: 50%;
  border: 1px solid white;
  transition: transform 0.7s;

  &:hover {
    transform: scale(1.2);
  }
}
</style>
