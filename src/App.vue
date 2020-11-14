<template>
  <div id="app">
    <graph v-bind:arrays="arrays"/>
  </div>
</template>

<script>
import graph from './components/Graph.vue'
import mockedData from './fixtures/mockData.json'

export default {
  name: 'App',
  data () {
    return {
      arrays: {
        meetings: mockedData.meetings,
        projects: mockedData.projects,
        investments: mockedData.investments
      },
    }
  },
  components: {
    'graph': graph,
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@100;300;400;500&display=swap');

html {
  font-family: 'Roboto', sans-serif;
}
</style>
