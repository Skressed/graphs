<template>
  <div id="card">
    <div id="graph">
      <svg :viewBox="viewBox">
        <g transform="translate(0, 10)">
          <path class="line meetingsLine" :d="meetingsLine"></path>
          <path class="line projectsLine" :d="projectsLine"></path>
          <path class="line investmentsLine" :d="investmentsLine"></path>
        </g>
      </svg>
    </div>
    <svg id="annotation" width="375" height="80">
      <circle cx="8" cy="15" r="4" fill="#ED5338"/><text x="40" y="20" fill="#111B42">Участвует в мероприятиях</text>
      <circle cx="8" cy="40" r="4" fill="#2EB349"/><text x="40" y="45" fill="#111B42">Участвует в проектах</text>
      <circle cx="8" cy="65" r="4" fill="#4E8EF8"/><text x="40" y="70" fill="#111B42">Инвестирует в проектах</text>
    </svg>
  </div>
</template>

<script>
import * as d3 from 'd3'

export default {
  name: 'Graph',
  props: {
    data: {
      type: Object,
    },
    width: {
      type: Number,
      default: 332,
    },
    height: {
      type: Number,
      default: 26,
    },
    margin: {
      type: Number,
      default: 15,
    }
  },
  computed: {
    rangeX() {
      const width = this.width;
      return [0, width];
    },
    rangeY() {
      const height = this.height - this.margin;
      return [height, 0];
    },
    meetingsLine() {
      return this.path(this.data.meetings);
    },
    projectsLine() {
      return this.path(this.data.projects);
    },
    investmentsLine() {
      return this.path(this.data.investments);
    },
    viewBox() {
      return `0 0 ${this.width} ${this.height}`;
    },
  },
  methods: {
    path(arr = []) {
      const x = d3.scaleLinear().range(this.rangeX);
      const y = d3.scaleLinear().range(this.rangeY);
      x.domain(d3.extent(arr, (d, i) => i));
      y.domain([0, d3.max(arr, d => d)]);
      return d3.line()
        .x((d, i) => x(i))
        .y(d => y(d))
        .curve(d3.curveMonotoneX)(arr);
    }
  },
}
</script>

<style>
#graph {
  margin: 25px;
  margin-top: 21px;
  margin-bottom: 8px;
}

#card {
  box-shadow: 0px 0px 15px rgba(0, 0, 0, 0.1);
  border-radius: 7px;
  display: inline-block;
  width: 375px;
  height: 143px;
}

#annotation {
  margin-left: 26px;
}

.meetingsLine {
    stroke: #ED5338;
}

.projectsLine {
    stroke: #2EB349;
}

.investmentsLine {
    stroke: #4E8EF8;
}

.line {
  fill: none;
  stroke-width: 3;
}
</style>
