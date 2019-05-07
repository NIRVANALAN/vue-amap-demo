<template>
  <div id="chart"></div>
</template>
<script>
import echarts from "echarts";

export default {
  name: "chart",
  mounted() {
    var chart = echarts.init(document.getElementById("chart"));

    var option = {
      tooltip: {},
      legend: {
        data: ["销量"]
      },
      xAxis: {
        data: ["衬衫", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "袜子"]
      },
      yAxis: {},
      series: [
        {
          name: "销量",
          type: "bar",
          data: [5, 20, 36, 10, 10, 20]
        }
      ]
    };

    chart.setOption(option);
  }
};
</script>
<style>
#chart {
  position: relative;
  height: 100%;
  width: 100%;
}
</style>
