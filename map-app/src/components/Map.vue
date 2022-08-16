<template>
  <div id="mapContainer"></div>
</template>

<script>
import "leaflet/dist/leaflet.css";
import L from "leaflet";

export default {
  name: "LeafletMap",
  data() {
    return {
      map: null,
    };
  },
  mounted() {
    this.map = L.map("mapContainer").setView([46.05, 11.05], 5);
    L.tileLayer("http://{s}.tile.osm.org/{z}/{x}/{y}.png", {
      attribution:
        '&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors',
    }).addTo(this.map);
    //use a mix of renderers
    const customPane = this.map.createPane("customPane");
    const canvasRenderer = L.canvas({ pane: "customPane" });
    customPane.style.zIndex = 399; // put just behind the standard overlay pane which is at 400

    // Markers (N,E)
    L.marker([50, 14]).addTo(this.map);

    L.marker([53, 20]).addTo(this.map);
    L.marker([49.5, 19.5]).addTo(this.map);
    L.marker([49, 25]).addTo(this.map);
    L.marker([-10, 25]).addTo(this.map);
    L.marker([10, -25]).addTo(this.map);
    L.marker([43.01, -7.57]).bindPopup("this is lugo").openPopup().addTo(this.map);
    L.marker([43.01, -7.57]).bindPopup("this is lugo").openPopup().addTo(this.map);
  },
  onBeforeUnmount() {
    if (this.map) {
      this.map.remove();
    }
  },
};
</script>

<style scoped>
#mapContainer {
  width: 100vw;
  height: 100vh;
}
</style>
