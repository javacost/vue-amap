<template>
  <div class="amap-page-container">
    <el-amap vid="amapDemo" :zoom="zoom" :center="center" class="amap-demo">
      <el-amap-marker
        v-for="(marker, index) in markers"
        :position="marker.position"
        :vid="index"
        key="index"
        >
      </el-amap-marker>
    </el-amap>
    <div class="toolbar">
      <button type="button" name="button" v-on:click="changePosition">change position</button>
    </div>
  </div>
</template>

<style>
  .amap-demo {
    height: 300px;
  }
</style>

<script>
  module.exports = {
    data() {
      return {
        lont: 121.0,/*经度*/
        lat: 31.0,/*纬度*/
        lola: [],
        zoom: 14,
        center: [],
        markers: [{position: []}],
      };
    },

    created() {
      this.changeData();
    },

    methods: {
      changePosition() {
        this.lont += 0.002;
        this.lat -= 0.002;
        this.changeData();
      },

      changeData() {
        this.lola.push(this.lont);
        this.lola.push(this.lat);
        this.markers[0].position = this.center = this.lola;
        this.lola = [];
      }
    }
  };
</script>
