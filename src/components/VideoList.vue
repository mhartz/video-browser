<template>
  <div>
    <h2>Video List</h2>
    <ul>
      <VideoListItem
        v-for="video in videos"
        :video="video"
      >
      </VideoListItem>
    </ul>
  </div>
</template>

<script>
import VideoListItem from './VideoListItem';

  export default {
    name: 'VideoList',
    components: {
      VideoListItem
    },
    data() {
      return {
        video: {}
      }
    },
    props: {
      videos: Array
    }
  }
</script>


<style>
</style>
