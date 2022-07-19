<template lang="">
  <nav class="filter-nav">
    <button
      :class="`${current == 'all' ? 'active' : ''}`"
      @click="updateFilter('all')"
    >
      View All
    </button>
    <button
      :class="`${current == 'completed' ? 'active' : ''}`"
      @click="updateFilter('completed')"
    >
      Completed
    </button>
    <button
      :class="`${current == 'ongoing' ? 'active' : ''}`"
      @click="updateFilter('ongoing')"
    >
      On going
    </button>
  </nav>
</template>
<script>
export default {
  props: ['current'],
  data() {
    return {}
  },
  methods: {
    updateFilter(by) {
      this.$emit('filterChange', by)
    },
  },
}
</script>
<style lang="css">
.filter-nav button {
  background: none;
  border: none;
  color: #bbb;
  outline: none;
  font-size: 12px;
  text-transform: uppercase;
  margin-right: 10px;
  letter-spacing: 1px;
  font-weight: bold;
  cursor: pointer;
}
.filter-nav button.active {
  color: #555;
}
</style>
