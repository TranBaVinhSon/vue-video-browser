<template lang="html">
  <div>
    <input @input="onInput" placeholder="type here..." />
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  methods: {
    onInput: function(event) {
      console.log(event.target.value);
      this.$emit("termChange", event.target.value);
    }
  }
};
</script>

<style lang="css" scoped>
  input {
    width: 75%;
    padding: 10px;
    border-radius: 5px;
  }
  div {
    text-align: center;
    margin: 20px;
  }
</style>
