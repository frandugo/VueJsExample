<template lang="pug">
  #app
    img(src='./assets/logo.png')
    ul
      artist(v-for"artist in artists" v-bind:artist="artist" )
</template>

<script>
import Artist from './components/Artist'
import getArtists from './api'
export default {
  name: 'app',
  data () {
    return {
      artists: []
    }
  },
  components:{
    Artist: Artist
  },
  mounted: function () {
    const self = this
    getArtists()
      .then(function (artists) {
        self.artists = artists
      })
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  p{
    color: #ccc;
    font-size: 40px;
  }
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
