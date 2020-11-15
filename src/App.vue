<template>
  <div id="app">
    <graph v-bind:data="data"/>
  </div>
</template>

<script>
import graph from './components/Graph.vue'
import mockedData from './fixtures/mockData.json'

export default {
  name: 'App',
  data () {
    return {
      timerId: 0,
      data: mockedData[0],
    }
  },
  created () {
    this.timerId = setInterval(this.setData, 3000);
  },
  methods: {
    setData() {
      const currentIndex = mockedData.indexOf(this.data);
      if (currentIndex === mockedData.length-1) {
        this.data = mockedData[0];
        return;
      }
      this.data = mockedData[currentIndex + 1];
    }
  },
  components: {
    'graph': graph,
  },
  destroyed() {
    clearInterval(this.timerId);
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro:wght@300&display=swap');

html {
  font-family: 'Source Sans Pro', sans-serif;
  font-size: 14px;
}
</style>
