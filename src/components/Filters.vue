<template>
  <div>
    <button type="button" @click="retrievalOrder" :disabled="isClicked">Order By Retrieval</button>
    &nbsp&nbsp<button @click="resetOrder" :disabled="!isClicked">Reset</button>
  </div>
</template>

<script>
export default {
  name: 'Filters',
  data() {
    return {
      isClicked: false
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
    }
  },
  computed: {
    isDisabled: function() {
      return !this.isClicked
    }
  }
}
</script>

<style scoped>
</style>
