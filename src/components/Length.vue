<template>
  <div>
    <h2>Lengths: </h2>
    <ol>
      <li v-for="length in this.lengths">
        {{length.lengthy}} {{length.measurement}}
      </li>
    </ol>
  </div>
</template>

<script>
  export default {
    name: 'Length',
    props: {
      lengths: {
        type: Array,
        required: true
      }
    }
  }
</script>