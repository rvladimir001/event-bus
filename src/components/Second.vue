<template>
  <div>
    <h1>Secont component</h1>
    <div>
      <input type="text" v-model="newName">
      <button @click.prevent="changeFromSecond()">Click!!</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Second",
  data() {
    return {
      newName: ''
    }
  },

  methods: {
    changeFromSecond() {
      this.$eventHub.$emit('change-from-second', this.newName);
    }
  }
}
</script>

<style scoped>

</style>
