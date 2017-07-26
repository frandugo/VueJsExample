<template lang="pug">
  li
    h2: a(:href="artist.url" target="_blank"){{ artist.name }}
    img(:src="artist.image[2]['#text']")
</template>

<script>
export default {
  name: 'artist',
  props: ['artist']
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
li{
  display: block;
  margin: 10px 0;
}
</style>
