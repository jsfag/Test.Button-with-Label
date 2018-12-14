<template>
  <div id="app">

    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->

    <ButtonLabel/>

  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import ButtonLabel from './components/ButtonLabel.vue'

export default {
  name: 'app',
  components: {
    ButtonLabel
  }
}
</script>

<style>
#app {
  /* background-color: blue; */
  display: flex;
  flex: 1;
  justify-content: center;
  align-items: center;
}
</style>
