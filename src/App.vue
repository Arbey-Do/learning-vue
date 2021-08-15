<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <Title message="BankApp el mejor banco del mundo!"/>
  <Account />
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Title from './components/Title.vue'
import Account from './components/Account.vue'

export default {
  name: 'App',
  components: {
    Title,
    Account
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}
</style>
