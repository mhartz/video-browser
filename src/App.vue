<template>
    <div>
        <SearchBar @termChange="onTermChange"></SearchBar>
        <VideoList :videos="videos"></VideoList>
    </div>
</template>

<script>
/* eslint-disable */
import axios from 'axios';
import SearchBar from './components/SearchBar';
import VideoList from './components/VideoList';

const API_KEY = "AIzaSyBunxJMtTrENCJjl5aRvjVb1MdqK4i68w8";

export default {
  name: "App",
  components: {
    SearchBar,
    VideoList
  },
  data() {
      return {
          videos: []
      }
  },
  methods: {
    onTermChange(searchTerm) {
        axios.get('https://www.googleapis.com/youtube/v3/search', {
            params: {
                key: API_KEY,
                type: 'video',
                part: 'snippet',
                q: searchTerm
            }
        }).then(response => {
            this.videos = response.data.items
        });
    }
  }
};
</script>

<style>
</style>
