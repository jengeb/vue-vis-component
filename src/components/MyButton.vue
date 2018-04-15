<template>
  <div class="hello">
    <h1>{{ title }}</h1>
    <h2>{{ question }}</h2>
    <button @click="onClick" class="Button">
      <slot>Button</slot>
    </button>
  </div>
</template>

<script>
export default {
  name: 'MyButton',
  props: {
    title: String,
    question: String,
    onClick: {
      type: Function,
      required: true
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
