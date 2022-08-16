<script setup lang="ts">
defineProps<{
  msg: string
}>()
// https://gis.stackexchange.com/questions/402871/custom-maps-in-leaflet-with-maptiler-and-geojson
// http://jsfiddle.net/davido/r2ms3dnp/
// https://blog.mastermaps.com/2013/06/showing-zoomify-images-with-leaflet.html
// https://leafletjs.com/examples/crs-simple/crs-simple.html
// https://leafletjs.com/reference.html#tilelayer-url-template
// https://codesandbox.io/examples/package/leaflet
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
    <h3>
      You’ve successfully created a project with
      <a target="_blank" href="https://vitejs.dev/">Vite</a> +
      <a target="_blank" href="https://vuejs.org/">Vue 3</a>. What's next?
    </h3>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
