<template>
  <div class="search-wrapper">
    <a-input placeholder="Basic usage" />
    <a-button type="primary" shape="circle" icon="search" />
  </div>
</template>

<script>
export default {
  methods: {
    onSearch(value) {
      console.log(value);
    },
  },
};
</script>
<style lang="css" scoped>
.search-wrapper {
  width: 300px;
  margin: 0 auto;
  display: flex;
}
</style>