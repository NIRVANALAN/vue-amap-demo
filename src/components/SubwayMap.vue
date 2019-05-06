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
        /* Station marker example
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
        */
        /* Custom info window example
        mysubway.addInfoWindow("南锣鼓巷", {
          isCustom: true,
          content: `
          <div class="tip_out">
            <div class="tip">
              <div class="tip_name">南锣古巷</div>
              <div class="tip_footer"></div>
            </div>
          </div>
          `
        });
        */
        /* Custom station example
        var detailOpts = {
          type: "circle",
          r: 14,
          customClass: "custom_circle"
        };

        mysubway.addCustomNode("南锣鼓巷", detailOpts);
        */
        mysubway.showLine("2号线");

        var $select_obj = document.getElementById("g-select");
        mysubway.setFitView($select_obj);
        var center = mysubway.getSelectedLineCenter();
        mysubway.setCenter(center);
      });
    });
  }
};
</script>
<style>
/* Custom info window example
.tip_out {
  position: relative;
}
.tip {
  position: absolute;

  width: 120px;
  left: -60px;
  bottom: 0;
}
.tip_name {
  background: rgba(0, 0, 0, 0.7);
  padding: 10px 0;
  text-align: center;
  font-size: 12px;
  color: #fff;
  border-radius: 4px;
}
.tip .tip_start,
.tip .tip_end {
  float: left;
}
.tip_footer {
  height: 10px;
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABcAAAALCAYAAACUPhZAAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAG5JREFUeNpiNDY2FmNgYJgDxFIM1AOvgDidCcpIAeJn1DQYiB8zIQlQwwK4wSAOE5oEJRagGIxuOCUWYBiMzXByLMBqMC7DSbEAp8H4DCfGArwGEzIcnwUEDSbGcGwWEGUwsYYjW3CBWINBACDAACkeLdxbVjieAAAAAElFTkSuQmCC)
    center top no-repeat;
  background-size: 21px 10px;
}
*/
.custom_circle {
  width: 30px;
  height: 30px;
  fill: rgb(0, 122, 255);
  fill-opacity: 0.4;
  stroke-width: 0;
}
</style>
