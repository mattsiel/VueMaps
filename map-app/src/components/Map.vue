<script>
import "leaflet/dist/leaflet.css";
import L from "leaflet";
// import data from "./Historic-Landmarks.json";

// https://gis.stackexchange.com/questions/402871/custom-maps-in-leaflet-with-maptiler-and-geojson

export default {
  name: "Vue-Map",
  data() {
    return {
      center: [37, 7749, -122, 4194],
    };
  },
  methods: {
    setupLeafletMap: function () {
        
      const mapDiv = L.map("mapContainer");
      L.tileLayer(
        "../../public/spain.geojson",
        {
          maxZoom: 18,
        }
      ).addTo(mapDiv);
    },
  },
  mounted() {
    this.setupLeafletMap();
  },
};
</script>

<template>
  <div id="container">
    <div id="mapContainer"></div>
  </div>
</template>

<style scoped>
    #mapContainer {
    width: 80vw;
    height: 100vh;
    }
</style>
