<template>
  <div id="card">
    <div id="graph">
      <svg :viewBox="viewBox">
        <g transform="translate(0, 10)">
          <path class="meetingsLine" :d="meetingsLine"></path>
          <path class="projectsLine" :d="projectsLine"></path>
          <path class="investmentsLine" :d="investmentsLine"></path>
        </g>
      </svg>
    </div>
    <svg id="annotation" width="375" height="80">
      <circle cx="8" cy="15" r="5" fill="#ED5338"/><text x="40" y="20">Участвует в мероприятиях</text>
      <circle cx="8" cy="40" r="5" fill="#2EB349"/><text x="40" y="45">Участвует в проектах</text>
      <circle cx="8" cy="65" r="5" fill="#4E8EF8"/><text x="40" y="70">Инвестирует в проектах</text>
    </svg>
  </div>
</template>

<script>
import * as d3 from 'd3'

// свойства svg контейнера
//const colors = ['lineR', 'lineG', 'lineB'];

export default {
  name: 'Graph',
  props: {
    arrays: {
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
      const width = this.width - this.margin;
      return [0, width];
    },
    rangeY() {
      const height = this.height - this.margin;
      return [height, 0];
    },
    meetingsLine() {
      return this.path(this.arrays.meetings);
    },
    projectsLine() {
      return this.path(this.arrays.projects);
    },
    investmentsLine() {
      return this.path(this.arrays.investments);
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
        .curve(d3.curveMonotoneX);
    }
    /*createGraph() {
      // применяем svg внутри body элемента
      const svg = d3.select(document.getElementById('graph'))
        .append('svg')
          .attr('width', WIDTH)
          .attr('height', HEIGHT)
        .append('g')
          .attr("transform", `translate(0,${MARGIN/2})`);

      this.arrays.forEach((item, i) => {
        // выбираем самое высокое и самое низкое значения для корректного масштабирования
        const highPeakPoints = Math.max.apply(Math, item);
        const lowPeakPoints = Math.min.apply(Math, item);

        const { length } = item;
        // строим кривую применяя масштабирование
        const currentLine = d3.line()
          .x((d, i) => ( d3.scaleLinear().domain([0, length-1]).range([0, WIDTH])(i) )) // масштабирование связывает первый элемент и левую границу, и последний элемент с правой границей
          .y(d => (d3.scaleLinear().domain([[lowPeakPoints],[highPeakPoints]]).range([HEIGHT-MARGIN, 0])(d.y)) ) // аналогично мин элемент в массиве = нижняя граница, макс элемент = верхняя
          .curve(d3.curveMonotoneX) // сглаживаем кривую


        // строим датасет из Y значений
        const currentDataset = d3.range(length).map(d => ({ "y": this.arrays[i][d] }));

        // привязываем датасет, вызываем строитель line
        svg.append('path')
          .datum(currentDataset)
          .attr('class', colors[i])
          .attr('d', currentLine);
      });
    }*/
  },
  mounted () {
    //this.createGraph();
  }
}
</script>

<style>
#graph {
  margin: 24px;
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
  margin-bottom: 12px;
}

.meetingsLine {
    fill: none;
    stroke: #ED5338;
    stroke-width: 3;
}

.projectsLine {
    fill: none;
    stroke: #2EB349;
    stroke-width: 3;
}

.investmentsLine {
    fill: none;
    stroke: #4E8EF8;
    stroke-width: 3;
}
</style>
