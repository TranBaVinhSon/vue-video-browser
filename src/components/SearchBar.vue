<template lang="html">
  <div>
    <input @input="onInput" />
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  data: {},
  methods: {
    onInput: function(event) {
      console.log(event.target.value);
      this.$emit("termChange", event.target.value);
    }
  }
};
</script>

<style lang="css">
</style>
