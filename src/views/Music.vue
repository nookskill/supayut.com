<template>
  <div class="music">
    <h1>My song</h1>
    <div class="box" v-for="item in data">

      <b>title: {{item.title}}</b><br>
      <b>artist: {{item.artist}}</b><br>
      <b>writer: {{item.writer}}</b><br>
      <b>soundcloud: {{item.soundcloud}}</b><br>
      <b>itunes: {{item.itunes}}</b><br>
      <b>applemusic: {{item.applemusic}}</b><br>
      <b>spotify: {{item.spotify}}</b><br>
      <b>youtube: {{item.youtube}}</b><br>
      <b>date: {{item.date}}</b><br>
      <b>description: {{item.description}}</b><br>
    </div>
    <div class="empty-box"></div>
  </div>
</template>

<script>
  import axios from 'axios';
  export default {
    data() {
      return {
        data: [],
      }
    },
    mounted () {
      axios
        .get('/music.json')
        .then(response => (this.data = response.data.songs))
    }
  }
</script>

<style>
  .box {
    text-align: left;
    border: #42b983;
    border-style: dotted;
    padding: 15px;
    margin-bottom: 15px;
  }
  .empty-box {
    margin-top: 100px;
  }
</style>