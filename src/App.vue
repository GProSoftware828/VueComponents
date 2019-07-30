<template>
  <div id="app">
    <h1>Ordered By Storge</h1>
    <ol>
      <li v-for="pipe in pipes">
        {{pipe.color}} {{pipe.length}}
      </li>
    </ol>
    <h2>Last In, First Out:</h2>
    <Filters @retrievalOrder="reverseOrder" @resetOrder="originalOrder"></Filters>
  </div>
</template>

<script>
import Filters from './components/Filters.vue'

export default {
  name: 'app',
  data() {
    return {
      pipes: [
        {color: 'green', length: 'long'},
        {color: 'blue', length: 'medium'},
        {color: 'lightBlue', length: 'long'},
        {color: 'red', length: 'short'}
      ]
    }
  },
  methods: {
    reverseOrder() {
      this.pipes.reverse()
    },
    originalOrder() {
      this.pipes.reverse()
    }
  },
  components: {
    Filters
  }
}
</script>

<style>
</style>
