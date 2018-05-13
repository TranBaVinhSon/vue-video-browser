<template lang="html">
  <div class="container">
    <SearchBar @termChange="onTermChange"></SearchBar>
    <VideoDetail v-bind:video="selectedVideo"></VideoDetail>

    <VideoList
      @videoSelect="onVideoSelect"
      :videos="videos">
    </VideoList>
  </div>
</template>

<script>
import axios from "axios";

import SearchBar from "./components/SearchBar";
import VideoList from "./components/VideoList";
import VideoDetail from "./components/VideoDetail";

const API_KEY = "AIzaSyCjdYfzlj9Z3Ye4N1x9iO1dGGT1ChNxHak";
export default {
  name: "App",
  components: {
    SearchBar: SearchBar,
    VideoList: VideoList,
    VideoDetail: VideoDetail
  },
  data: function() {
    return { videos: [], selectedVideo: null };
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
      }).then(response => {
        this.videos = response.data.items;
      });
    },
    onVideoSelect(video) {
      console.log(video);
      this.selectedVideo = video;
    }
  }
}
</script>

<style lang="css">
</style>
