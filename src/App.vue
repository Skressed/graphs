<template>
  <div id="app">
    <navbar/>
    <card v-bind:data="data"/>
  </div>
</template>

<script>

import card from './components/Card.vue'
import navbar from './components/Navbar.vue'
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
    'card': card,
    'navbar': navbar,
  },
  destroyed() {
    clearInterval(this.timerId);
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro:wght@300;400;600&display=swap');

html {
  background-color: #F5F5F5;
  font-family: 'Source Sans Pro', sans-serif;
  font-size: 14px;
  font-weight: 300;
  color: #111B42;
}

#app {
  background-color: #F5F5F5;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
