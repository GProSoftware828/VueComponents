<template>
  <div>
    <button type="button" @click="retrievalOrder" :disabled="isClicked">Order By Retrieval</button>
    &nbsp&nbsp<button @click="resetOrder" :disabled="!isClicked">Reset</button>
    &nbsp&nbsp<button @click="emitGlobalClickEvent()">Click Me For Event Bus</button>
    <button type="button" @click="isShown = !isShown">Toggle</button>
    <transition name="fade">
      <p v-if="isShown" key="showThis">Ex of transitions</p>
    </transition>
    <button @click="addRandom">Add Random Number</button>
    <button @click="removeRandom">Remove Random Number</button>
    <span class="list-item" v-for="n in numbers">{{n}}</span>
  </div>
</template>

<script>
import {eventBus} from '../main';

export default {
  name: 'Filters',
  data() {
    return {
      isShown: false,
      isClicked: false,
      quantity: [
        {green: 8},
        {blue: 4},
        {lightBlue: 1},
        {red: 3}
      ],
      clickCount: 0,
      numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
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
    },
    getRandomIndex() {
      return Math.floor(Math.random() * this.numbers.length);
    },
    addRandom() {
      let randomNumber = Math.floor(Math.random() * 100);
      this.numbers.splice(this.getRandomIndex(), 0, randomNumber);
    },
    removeRandom() {
      this.numbers.splice(this.getRandomIndex(), 1);
    }
  }
}
</script>

<style scoped>
  .fade-enter, .fade-leave-to {
    opacity: 0;
  }

  .fade-enter-active, .fade-leave-active {
    transition: opacity 2s;
    transition-duration: 3s;
  }

  .list-item {
    display: inline-block;
    margin-right: 10px;
  }
</style>
