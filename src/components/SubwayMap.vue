<template>
  <div id="mysubway"></div>
</template>
<script>
export default {
  name: "SubwayMap",
  mounted() {
    var mysubway = null;
    window.addEventListener("load", () => {
      mysubway = window.subway("mysubway", { easy: 1 });
      mysubway.event.on("subway.complete", () => {
        /* Info window example
        mysubway.addInfoWindow("南锣鼓巷");
        var center = mysubway.GetStCenter("南锣鼓巷");
        mysubway.setCenter(center);
        */
        var marker1 = mysubway.addMarker("南锣鼓巷", {});
        var marker2 = mysubway.addMarker("北海北", {
          width: 19,
          height: 33,
          offset: {
            x: 0,
            y: 0
          },
          cnt: `
          <div>
            <img src="https://webapi.amap.com/theme/v1.3/markers/n/mark_bs.png">
          </div>
          `
        });
      });
    });
  }
};
</script>
<style>
</style>
