<template>
  <div id="app">
    <Menu />
    <Viewer :colors="colors" @showDetail="showDetail" />
    <Detail v-if="detail" :color="detail" @close="close"/>
  </div>
</template>

<script>
import Viewer from './components/Viewer'
import Menu from './components/Menu'
import Detail from './components/Detail'
import axios from 'axios'

export default {
  name: 'app',
  components: {
    Viewer,
    Menu,
    Detail
  },
  data () {
    return {
      colors: false,
      detail: false
    }
  },
  created () {
    axios.get('http://localhost:5000/colors.json').then(res => {
      this.colors = res.data
    })
  },
  methods: {
    showDetail (data) {
      this.detail = data
    },
    close () {
      this.detail = false
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  /* margin-top: 60px; */
}

@keyframes fadeIn {
  0% {opacity: 0;}
}
</style>
