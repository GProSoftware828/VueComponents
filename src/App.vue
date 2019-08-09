<template>
  <div id="app">
    <h1>Ordered By Storge</h1>
    <ol>
      <li v-for="pipe in pipes">
        <button>{{pipe.color}} {{pipe.length}}</button>
      </li>
    </ol>
    <h2>Last In, First Out:</h2>
    <Filters @retrievalOrder="reverseOrder" @resetOrder="originalOrder"></Filters>
    <Length v-bind:lengths="lengths"></Length>
  </div>
</template>

<script>
import Filters from './components/Filters.vue';
import Length from './components/Length.vue';

export default {
  name: 'app',
  data() {
    return {
      pipes: [
        {color: 'green', length: 'long'},
        {color: 'blue', length: 'medium'},
        {color: 'lightBlue', length: 'long'},
        {color: 'red', length: 'short'}
      ],
      lengths: [
        {lengthy: 'short', measurement: '12 feet'},
        {lengthy: 'medium', measurement: '18 feet'},
        {lengthy: 'long', measurement: '25 feet'}
      ],
      amount: [
        {color: 'green', quantity: '5'},
        {color: 'blue', quantity: '3'},
        {color: 'lightBlue', quantity: '2'},
        {color: 'red', quantity: '2'}
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
    'Filters' : Filters,
    'Length': Length
  }
}
</script>

<style>

</style>
