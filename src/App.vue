<template lang="html">
  <div>
    <SearchBar @termChange="onTermChange"></SearchBar>

  </div>
</template>

<script>
import SearchBar from "./components/SearchBar";
export default {
  name: "App",
  components: {
    SearchBar: SearchBar
  },
  methods: {
    onTermChange(searchTerm) {
      console.log(searchTerm);
    }
  }
}
</script>

<style lang="css">
</style>
