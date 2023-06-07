<template>
  <GreetingMessage name="Kraig"/>
  <GreetingMessage :name="name"/>
</template>

<script>

import GreetingMessage from './components/GreetingMessage.vue';

export default {
    name: "App",

    components: {
      GreetingMessage,
    },

    data() {
      return {
        name: 'Omondi'
      }
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
  margin-top: 60px;
}
</style>
