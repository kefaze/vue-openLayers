<template>
  <div id="mapContainer" ref="rootmap">
    openlayer 实例
  </div>
</template>

<script>
import 'ol/ol.css'

import {Map, View} from "ol"
import TileLayer from "ol/layer/Tile"
import OSM from "ol/source/OSM"

export default {
  data () {
    return {
      map: null
    }
  },
  mounted () {
    var mapcontainer = this.$refs.rootmap

    this.map = new Map({
      target: "mapContainer",
      layers: [
        new TileLayer({
          source: new OSM()
        })
      ],
      view: new View({
        projection: "EPSG:4326",
        center: [108.5, 33.9],
        zoom: 10
      })
    })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
