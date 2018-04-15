<template>
  <div id="app">
    <MyButton
      title="message of component"
      question="your question"
      :onClick="consoleClick"
      v-bind:data="{ id: 1, title: 'My Journey with Vue' }"
    />
  </div>
</template>

<script>
import MyButton from './components/MyButton.vue'

export default {
  name: 'app',
  components: {
    MyButton
  },
  methods: {
    consoleClick() {
      console.log('Button clicked')
    },
    alertClick() {
      alert('Button clicked')
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
