<template>
    <div ref="mapContainer" class="map-container"></div>
</template>

<script>
import mapboxgl from "mapbox-gl";
mapboxgl.accessToken = "pk.eyJ1IjoiZWxpbmVhciIsImEiOiJjbG9jeGRzcWkwMXV4Mm1ueW0wY2g4bWZ3In0.ILk87MZMtJpRO0TzguWD6g"

export default {
    mounted() {
  const map = new mapboxgl.Map({
    container: this.$refs.mapContainer,
    style: "mapbox://styles/elinear/clrjm447m000701p1e5y7awrc", // Replace with your preferred map style
    center: [-87.844, 41.790],
    zoom: 9,
  });
  

  this.map = map;
},
unmounted() {
  this.map.remove();
  this.map = null;
}
};
</script>

<style>
.map-container {
  flex: 1;
}
</style>
