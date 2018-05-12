<template lang="html">
  <div>
    <SearchBar @termChange="onTermChange"></SearchBar>

  </div>
</template>

<script>
import SearchBar from "./components/SearchBar";
import axios from "axios";

const API_KEY = "AIzaSyCjdYfzlj9Z3Ye4N1x9iO1dGGT1ChNxHak";
export default {
  name: "App",
  components: {
    SearchBar: SearchBar
  },
  methods: {
    onTermChange(searchTerm) {
      axios.get("https://www.googleapis.com/youtube/v3/search", {
        params: {
          key: API_KEY,
          type: "video",
          part: "snippet",
          q: searchTerm
        }
      }).then(response => console.log(response));
    }
  }
}
</script>

<style lang="css">
</style>
