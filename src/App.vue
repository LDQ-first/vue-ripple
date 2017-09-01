<template>
  <div id="app">
    <show></show>
  </div>
</template>

<script>
import Show from './views/show.vue'

export default {
  name: 'app',
  components: {
    Show
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

html {
  height: 100%;
}

body {
  background: linear-gradient(135deg,
   rgba(104, 201, 182, 1), rgba(54, 119, 206, 1)) no-repeat;
  background-attachment: fixed;
  height: 100%;
}

button {
  cursor: pointer;
  border: none;
  outline: none;
  -webkit-appearance: none;
  color: #fff;
  margin: 12px;
  background: #7e57c2;
  border-radius: 2px;
  height: 36px;
  line-height: 36px;
  padding: 0;
  min-width: 88px;
  box-shadow: 0 1px 6px rgba(0,0,0,.117647),
              0 1px 4px rgba(0,0,0,.117647);
}
</style>
