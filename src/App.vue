<template>
  <div id="app">
    <NavBar />
    <router-view/>
  </div>
</template>

<script>
import NavBar from '@/components/NavBar'

export default {
  name: 'App',
  data() {
    return {

    }
  },
  components: {
    NavBar
  }
}
</script>


<style lang="scss">
#app {
  font-family: Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-size: 14px;
  line-height: 18px;
  font-weight: 300;
  text-align: center;
  color: #2c3e50;
  background-color: #eee;
}
.btn-primary {
  padding: 5px 20px;
  background-color: cornflowerblue;
}
</style>
