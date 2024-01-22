<template>
    <div ref="mapContainer" class="map-container"></div>
</template>

<script>
import mapboxgl from "mapbox-gl";
mapboxgl.accessToken = os.environ("MAPBOX_ACCESS_TOKEN")

export default {
    mounted() {
  const map = new mapboxgl.Map({
    container: this.$refs.mapContainer,
    style: os.environ("MAPBOX_STYLE"),
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
