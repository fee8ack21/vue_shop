<template>
  <main class="main-location">
    <div class="container py-5">
      <div class="row">
        <div class="col-3">
          <ul class="list-unstyled">
            <LocationContentAccordion />
            <LocationContentAccordion />
            <LocationContentAccordion />
          </ul>
        </div>
        <div class="col-9">
          <div id="map" class="embed-responsive embed-responsive-16by9"></div>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import LocationContentAccordion from './LocationContentAccordion.vue';
/* global google */
export default {
  name: 'LocationContent',
  data() {
    return {
      map: null,
      // 預設經緯度在信義區附近
      marker: null,
      lat: 25.0325917,
      lng: 121.5624999,
    };
  },
  mounted() {
    this.initMap();
    this.setMarker();
  },
  methods: {
    // 建立地圖
    initMap() {
      // 透過 Map 物件建構子建立新地圖 map 物件實例，並將地圖呈現在 id 為 map 的元素中
      this.map = new google.maps.Map(document.getElementById('map'), {
        // 設定地圖的中心點經緯度位置
        center: { lat: this.lat, lng: this.lng },
        // 設定地圖縮放比例 0-20
        zoom: 15,
        // 限制使用者能縮放地圖的最大比例
        maxZoom: 20,
        // 限制使用者能縮放地圖的最小比例
        minZoom: 3,
        // 設定是否呈現右下角街景小人
        streetViewControl: false,
        // 設定是否讓使用者可以切換地圖樣式：一般、衛星圖等
        mapTypeControl: false,
      });
    },
    // 建立地標
    setMarker() {
      // 建立一個新地標
      this.marker = new google.maps.Marker({
        // 設定地標的座標
        position: { lat: this.lat, lng: this.lng },
        // 設定地標要放在哪一個地圖
        map: this.map,
      });
    },
  },
  components: {
    LocationContentAccordion,
  },
};
</script>

<style lang="scss">
.main-location {
  min-height: calc(100vh - 152px);
  & > div {
    min-height: calc(100vh - 152px);
  }
  iframe {
    min-height: calc(100vh - 248px);
  }
}
</style>
