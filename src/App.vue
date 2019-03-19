<template>
  <div class="app">
    <myamap></myamap>
  </div>
</template>

<script>

  import {AMapManager} from 'vue-amap';
  import myamap from './components/myamap'
  // var coordtransform = require('coordtransform/index');

  export default {
    data: function () {
      return {}
    },
    components: {
      myamap
    }
  }
</script>

<style>
  .app {
    width: 300px;
    height: 300px;
  }

  .amap-page-container{
    height: 100%;
  }
</style>
