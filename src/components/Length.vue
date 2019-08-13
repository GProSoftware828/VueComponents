<template>
  <div>
    <h2>Lengths: </h2>
    <button @click="isShown = !isShown">Show or Hide</button>
    <ol>
      <li v-show="isShown" v-for="length in this.lengths">
        {{length.lengthy}} {{length.measurement}}
      </li>
    </ol>
  </div>
</template>

<script>
import {eventBus} from '../main';

  export default {
    name: 'Length',
    props: {
      lengths: {
        type: Array,
        required: true
      }
    },
    data() {
      return {
      isShown: false,
      }
    },
    created() {
      eventBus.$on('i-got-clicked', clickCount => {
        alert(`Click number: ${clickCount}`)
      });
    }
  }
</script>

<style>
  .fade-enter, .fade-leave-to {
    opacity: 0;
  }

  .fade-enter-active, .fade-leave-active {
    transition: opacity 2s;
  }
</style>