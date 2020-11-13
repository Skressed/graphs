<template>
  <div id="card">
    <div id="graph"/>
    <svg id="annotation" width="375" height="80">
      <circle cx="8" cy="15" r="5" fill="#ED5338"/><text x="40" y="20">Участвует в мероприятиях</text>
      <circle cx="8" cy="40" r="5" fill="#2EB349"/><text x="40" y="45">Участвует в проектах</text>
      <circle cx="8" cy="65" r="5" fill="#4E8EF8"/><text x="40" y="70">Инвестирует в проектах</text>
    </svg>
  </div>
</template>

<script>
import * as d3 from 'd3'

export default {
  name: 'Graph',
  props: {
    arrays: {
      type: Array,
    }
  },
  methods: {
    createGraph() {
      let data = this.arrays;

      // свойства svg контейнера
      let width = 332;
      let height = 26;
      let margin = 10;

      let colors = ['lineR', 'lineG', 'lineB'];

      let highPeakPoints = [];
      let lowPeakPoints = [];
      let line = [];
      let dataset = [];

      // применяем svg внутри body элемента
      let svg = d3.select(document.getElementById('graph')).append("svg")
          .attr("width", width)
          .attr("height", height)
        .append("g")
          .attr("transform", "translate(" + 0 + "," + margin/2 + ")");

      for (let i=0; i<data.length; i++) {
        // выбираем самое высокое и самое низкое значения для корректного масштабирования
        highPeakPoints[i] = Math.max(...data[i]);
        lowPeakPoints[i] = Math.min(...data[i]);

        let arrLength = data[i].length;
        // строим кривую применяя масштабирование
        line[i] = d3.line()
          .x(function(d, i) { return d3.scaleLinear().domain([0, arrLength-1]).range([0, width])(i); }) // масштабирование связывает первый элемент и левую границу, и последний элемент с правой границей
          .y(function(d) { return d3.scaleLinear().domain([[lowPeakPoints[i]],[highPeakPoints[i]]]).range([height-margin,0])(d.y); }) // аналогично мин элемент в массиве = нижняя граница, макс элемент = верхняя
          .curve(d3.curveMonotoneX) // сглаживаем кривую

        // строим датасет из Y значений
        dataset[i] = d3.range(arrLength).map(function(d) { return {"y": data[i][d] } });

        // привязываем датасет, вызываем строитель line
        svg.append("path")
          .datum(dataset[i])
          .attr("class", colors[i])
          .attr("d", line[i]);
      }
    }
  },
  mounted () {
    this.createGraph();
  }
}
</script>

<style>
#graph {
  margin: 24px;
}

#card {
  box-shadow: 0px 0px 15px rgba(0, 0, 0, 0.1);
  border-radius: 7px;
  display: inline-block;
}

#annotation {
  margin-left: 26px;
  margin-bottom: 12px;
}

.lineR {
    fill: none;
    stroke: #ED5338;
    stroke-width: 3;
}

.lineG {
    fill: none;
    stroke: #2EB349;
    stroke-width: 3;
}

.lineB {
    fill: none;
    stroke: #4E8EF8;
    stroke-width: 3;
}
</style>
