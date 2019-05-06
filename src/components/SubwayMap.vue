<template>
  <div id="mysubway"></div>
</template>
<script>
export default {
  name: "SubwayMap",
  mounted() {
    window.addEventListener("load", () => {
      var mysubway = window.subway("mysubway", { easy: 1 });
    });
  }
};
</script>
<style>
</style>
