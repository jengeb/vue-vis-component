<template>
  <div id="app">
    <MyButton
      buttonText="text of button"
      question="your question"
      title="message of component"
      :onClick="consoleClick"
      v-bind:json="{
        data: [10,2,3,400,50,6,70,10],
        text: 'title *of* json ~~TODO~~ render __markdown__ Type **Markdown** here.'
      }"
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
  }
}
</script>

<style lang="sass">
@import '../node_modules/bootstrap/scss/bootstrap.scss'
</style>
