<template>
  <div style="height: 80vh">
    <LMap :zoom="zoom" :center="center">
      <LTileLayer :url="url"></LTileLayer>
      <LMarker v-for="supplier in suppliers" :key="supplier.id" :lat-lng="[supplier.latitude, supplier.longitude]"></LMarker>      
    </LMap>
  </div>
</template>
      
<script>
import { LMap, LTileLayer, LMarker} from "vue2-leaflet";

export default {
  name: "Map",
  props: ['suppliers'],
  components: {
    LMap,
    LTileLayer,
    LMarker
  },
  data() {
    return {
      url: "https://{s}.tile.osm.org/{z}/{x}/{y}.png",
      zoom: 6,
      center: [9, 11],
      bounds: null
    };
  }
};
</script>
