<template>
  <div class="hello">
    <h1>{{ title }}</h1>
    <h2>{{ question }}</h2>
    <button @click="onClick" class="Button">
      <slot>Button</slot>
    </button>
    <span>{{ data.title }}</span>
  </div>
</template>

<script>
import * as d3 from 'd3'

export default {
  name: 'MyButton',
  props: {
    title: String,
    question: String,
    onClick: {
      type: Function,
      required: true
    },
    data: Object
  },
  mounted: function() {
    console.log('mounted');
    var button = d3.select("button");
    console.log(button)
  }
}



</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
