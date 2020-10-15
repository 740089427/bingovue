<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-view/>
     <el-button @click="test">test</el-button>
     <el-dialog :visible=visible title="test"></el-dialog>
  </div>
</template>

<script>
export default {
  name: 'App',
  data: function () {
    return {
      visible: false
    }
  },
  methods: {
    test () {
      this.visible = true
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
