<template>
  <div id="app">
    <vue-h-zoom
      image="https://images.unsplash.com/photo-1518715318-e497b2fd1151?ixlib=rb-0.3.5&ixid=eyJhcHBfaWQiOjEyMDd9&s=fecf5e07748b5b3eb9b30636056dc3ea&w=1000&q=80"
      image-full="https://images.unsplash.com/photo-1518715318-e497b2fd1151?ixlib=rb-0.3.5&ixid=eyJhcHBfaWQiOjEyMDd9&s=fecf5e07748b5b3eb9b30636056dc3ea&w=1000&q=80"
      :zoom-level="2"
    ></vue-h-zoom>
  </div>
</template>

<script>
export default {
  name: "App",
  data: () => ({
    images: [
      "https://images.unsplash.com/photo-1518715318-e497b2fd1151?ixlib=rb-0.3.5&ixid=eyJhcHBfaWQiOjEyMDd9&s=fecf5e07748b5b3eb9b30636056dc3ea&w=1000&q=80",
    ],
  }),
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
