<template lang="html">
  <div v-if="video" class="col-md-8">
    <div class="embed-responsive embed-responsive-16by9">
      <iframe class="embed-responsive-item" v-bind:src="videoUrl" allowfullscreen></iframe>
    </div>
    <div class="details">
      <h4>{{ video.snippet.title }}</h4>
      <p>{{ video.snippet.description }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "VideoDetail",
  props: ["video"],
  computed: {
    videoUrl() {
      const videoId =  this.video.id.videoId;
      return `https://www.youtube.com/embed/${videoId}`;
    }
  }
}
</script>

<style lang="css" scoped>
  .details {
    margin-top: 5px;
    margin-bottom: 10px;
    padding: 10px;
    border-radius: 4px;
    border: 1px solid #ddd;
  }
</style>
