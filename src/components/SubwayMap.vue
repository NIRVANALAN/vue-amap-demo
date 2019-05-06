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
        mysubway.addInfoWindow("南锣鼓巷");
        var center = mysubway.GetStCenter("南锣鼓巷");
        mysubway.setCenter(center);
      });
    });
  }
};
</script>
<style>
</style>
