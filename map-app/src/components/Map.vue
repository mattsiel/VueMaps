<script>
import "leaflet/dist/leaflet.css";
import L from "leaflet";
// import data from "./Historic-Landmarks.json";

// https://gis.stackexchange.com/questions/402871/custom-maps-in-leaflet-with-maptiler-and-geojson
// http://jsfiddle.net/davido/r2ms3dnp/
// https://blog.mastermaps.com/2013/06/showing-zoomify-images-with-leaflet.html
// https://leafletjs.com/examples/crs-simple/crs-simple.html
export default {
 name: "VueMap",
 data() {
   return{
     center: [37,7749, -122,4194]
   }},
 methods: {
   setupLeafletMap: function () {
     const mapDiv = L.map("mapContainer").setView(this.center, 13);
     L.tileLayer(
       'https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png?{foo}',
       {
         attribution:
           'Map data (c) <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery (c) <a href="https://www.mapbox.com/">Mapbox</a>',
         maxZoom: 18,
         id: "mapbox/streets-v11",
         accessToken:"XXX"
       }
     ).addTo(mapDiv);
   },
 },
 mounted() {
   this.setupLeafletMap();
 },
};
</script>

<style scoped>
#mapContainer {
 width: 80vw;
 height: 100vh;
}
</style>