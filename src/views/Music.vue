<template>
  <div class="music">
    <h1>My song</h1>
    <div v-for="item in data">
      <div class="box-left"></div>
      <div class="box-main">
        <div>title: {{item.title}}</div>
        <div>artist: {{item.artist}}</div>
        <div>writer: {{item.writer}}</div>
        <div>soundcloud: {{item.soundcloud}}</div>
        <div v-if="item.itunes">itunes: <a v-bind:href="item.itunes">Click here</a></div>
        <div v-else>itunes: - </div>
        <div v-if="item.applemusic">applemusic: <a v-bind:href="item.applemusic">Click here</a></div>
        <div v-else>applemusic: - </div>
        <div v-if="item.spotify">spotify: <a v-bind:href="item.spotify">Click here</a></div>
        <div v-else>spotify: - </div>
        <div v-if="item.youtube">youtube: <a v-bind:href="item.youtube">Click here</a></div>
        <div v-else>youtube: - </div>
        <div>date: {{item.date}}</div>
        <div>description: {{item.description}}</div>
      </div>
      <div class="box-right"></div>
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
  .box-left {
    width: 20%;
  }

  .box-main {
    text-align: left;
    font-weight: bold;

    border: #42b983;
    border-style: dotted;
    padding: 15px;
    margin-bottom: 15px;
  }

  .box-right {
    width: 20%;
  }

  .empty-box {
    margin-top: 100px;
  }

  a {
    color: #c5c6c7;
  }

  @media only screen and (max-width: 540px) {
    .box-main {
      text-align: left;
      font-weight: bold;

      border: #42b983;
      border-style: dotted;
      padding: 15px;
      margin-bottom: 15px;
    }
    .empty-box {
      margin-top: 100px;
    }
  }
</style>