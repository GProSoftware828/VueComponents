<template>
  <div>
    <button type="button" @click="retrievalOrder" :disabled="isClicked">Order By Retrieval</button>
    &nbsp&nbsp<button @click="resetOrder" :disabled="!isClicked">Reset</button>
    &nbsp&nbsp<button @click="emitGlobalClickEvent()">Click Me For Event Bus</button>
  </div>
</template>

<script>
import {eventBus} from '../main';

export default {
  name: 'Filters',
  data() {
    return {
      isClicked: false,
      quantity: [
        {green: 8},
        {blue: 4},
        {lightBlue: 1},
        {red: 3}
      ],
      clickCount: 0
    }
  },
  created() {
    console.log(this.isClicked)
  },
  methods: {
    retrievalOrder: function() {
      this.$emit('retrievalOrder');
      this.isClicked = true;
      console.log(this.isClicked);
    },
    resetOrder: function() {
      this.$emit('resetOrder');
      this.isClicked = false;
      console.log(this.isClicked);
    },
    emitGlobalClickEvent() {
      this.clickCount++;
      eventBus.$emit('i-got-clicked', this.clickCount);
    }
  }
}
</script>

<style scoped>
</style>
