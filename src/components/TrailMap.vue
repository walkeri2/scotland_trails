<template lang="html">
  <head>

  </head>

    <script>
      var mymap = L.map('mapid').setView([51.505, -0.09], 13);

      L.tileLayer('https://api.mapbox.com/styles/v1/{id}/tiles/{z}/{x}/{y}?access_token={accessToken}', {
          attribution: 'Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
          maxZoom: 18,
          id: 'mapbox/streets-v11',
          tileSize: 512,
          zoomOffset: -1,
          accessToken: 'pk.eyJ1Ijoid2Fsa2VyNzUzOCIsImEiOiJjazZ6YmlzcWExM3h0M25tb2I1MTEzajZsIn0.CghieUDjQK9JkzXFP07_8A'
      }).addTo(mymap);
</template>

<script>
import{eventBus} from '../main.js'

export default {
  name: 'trail-map',
  props: ['map']
}

</script>

<style lang="css" scoped>
#mapid { height: 180px; }

</style>

<script src="https://unpkg.com/leaflet@1.6.0/dist/leaflet.js"
   integrity="sha512-gZwIG9x3wUXg2hdXF6+rVkLF/0Vi9U8D2Ntg4Ga5I5BZpVkVxlJWbSQtXPSiUTtC0TjtGOmxa1AJPuV0CPthew=="
   crossorigin=""></script>
