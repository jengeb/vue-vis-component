<template>
  <div class="visualization">
    <h1>{{ title }}</h1>
    <h2>{{ question }}</h2>
    <svg width="500" height="270">
      <g>
        <path :d="line" />
      </g>
    </svg>
    <button type="button" @click="onClick" class="btn btn-primary">
      {{ buttonText }}
    </button>
    <vue-markdown>{{ json.title }}</vue-markdown>
  </div>
</template>

<script>
import * as d3 from 'd3'
import VueMarkdown from 'vue-markdown'

export default {
  components: {
    VueMarkdown
  },
  name: 'MyButton',
  props: {
    title: String,
    question: String,
    buttonText: String,
    onClick: {
      type: Function,
      required: true
    },
    json: Object
  },
  data() {
    return {
      data: [40, 50, 10, 20, 90, 80, 100, 10, 90, 60, 120, 10, 0, 100, 10],
      line: '',
    };
  },
  mounted() {
    this.calculatePath()
  },
  methods: {
    getScales() {
      const x = d3.scaleTime().range([0, 400])
      const y = d3.scaleLinear().range([200, 0])
      d3.axisLeft().scale(x)
      d3.axisBottom().scale(y)
      x.domain(d3.extent(this.data, (d, i) => i))
      y.domain([0, d3.max(this.data, d => d)])
      return { x, y }
    },
    calculatePath() {
      const scale = this.getScales()
      const path = d3.line()
        .x((d, i) => scale.x(i))
        .y(d => scale.y(d))
      this.line = path(this.data)
    },
  }
}
</script>

<style scoped lang="sass">
svg
  path
    fill: none
    stroke: #64B5F6
    stroke-width: 2px

.visualization
  text-align: center
</style>
