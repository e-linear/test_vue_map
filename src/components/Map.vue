<template>
    <div ref="mapContainer" class="map-container"></div>
</template>

<script>
import mapboxgl from "mapbox-gl";
mapboxgl.accessToken = ""

export default {
    mounted() {
  const map = new mapboxgl.Map({
    container: this.$refs.mapContainer,
    style: "", // Replace with your preferred map style
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
