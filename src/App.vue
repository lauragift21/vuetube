<template>
  <div id="app">
    <div class="banner">
      <img
        src="https://cdn-images-1.medium.com/max/880/1*tidWIoAQ-i2SiKTNh9WJSw.png"
        style="margin: 14px; cursor: pointer;"
        width="100px"
        alt="logo"
      >
    </div>
    <VideoPlayer/>
  </div>
</template>

<script>
import VideoPlayer from "./components/VideoPlayer";

export default {
  name: "App",
  components: {
    VideoPlayer
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
