<template lang="html">
  <ul class="list-group col-md-4">
    <VideoListItem
      v-for="video in videos"
      :video="video"
      :key="video.etag"
      @videoSelect="onVideoSelect"
    >

    </VideoListItem>
  </ul>
</template>

<script>
import VideoListItem from "./VideoListItem";

export default {
  name: "VideoList",
  props: {
    videos: Array
  },
  components: {
    VideoListItem: VideoListItem
  },
  methods: {
    onVideoSelect(video){
      this.$emit("videoSelect", video);
    }
  }
}
</script>

<style lang="css">
</style>
