<template lang="html">
  <li class="list-group-item media" @click="onVideoSelect">
    <img class="mr-3" v-bind:src="this.thumbnailUrl" />
    <div class="media-body">
      {{video.snippet.title}}
    </div>
  </li>
</template>

<script>
export default {
  name: "VideoListItem",
  props: ["video"],
  computed: {
    thumbnailUrl() {
      return this.video.snippet.thumbnails.default.url;
    }
  },
  methods: {
    onVideoSelect() {
      console.log("fuck");
      this.$emit("videoSelect", this.video);
    }
  }
}
</script>

<style lang="css" scoped>
  li {
    display: flex;
    cursor: pointer;
  }
  li:hover {
    background-color: #eee;
  }
</style>
