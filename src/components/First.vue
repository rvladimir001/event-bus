<template>
  <div>
    <h1>First component</h1>
    <h1>Changed from second component - {{ name }}</h1>
  </div>
</template>

<script>
export default {
  name: "First",
  data() {
    return {
      name: 'This from first component'
    }
  },
  created() {
    this.$eventHub.$on('change-from-second', this.changeName)
  },
  beforeDestroy() {
    this.$eventHub.$off('change-from-second');
  },
  methods: {
    changeName(name) {
      this.name = name;
    }
  }
}
</script>

<style scoped>

</style>
