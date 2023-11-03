<template>
  <div>
    <div class="a">
      这一年你最喜欢在
      <span class="value"> {{ maxMonth[0] }} </span>晚上提交任务 提交了<span class="value">
        {{ maxMonth[1] }} </span>70条
    </div>
    <div ref="chart" class="chart"></div>
  </div>
</template>

<script>
import * as echarts from "echarts";
import { hourGroup } from "@/data.json";
export default {
  data() {
    return {
      myChart: undefined,
      arr: hourGroup,
      RECORDS: [
        {
          user_id: 34,
          user_name: "陈志云",
          time_period: "晚上18:00—24:00",
          job_count: 74
        },
        {
          user_id: 34,
          user_name: "陈志云",
          time_period: "凌晨00:00—5:00",
          job_count: 3
        },
        {
          user_id: 34,
          user_name: "陈志云",
          time_period: "傍晚17:00—18:00",
          job_count: 15
        },
        {
          user_id: 34,
          user_name: "陈志云",
          time_period: "中午11:00—13:00",
          job_count: 31
        },
        {
          user_id: 34,
          user_name: "陈志云",
          time_period: "下午13:00—17:00",
          job_count: 62
        },
        {
          user_id: 34,
          user_name: "陈志云",
          time_period: "上午8:00—11:00",
          job_count: 52
        }]
    };
  },
  computed: {
    maxMonth() {
      let max = this.arr[0];
      for (let i of this.arr) {
        if (i[1] > max[1]) {
          max = i;
        }
      }
      return max;
    },
  },
  mounted() {
    this.myChart = echarts.init(this.$refs.chart);
    this.myChart.setOption({
      dataset: {
        source: this.RECORDS
      },
      xAxis: {
        type: "category",
        axisLabel: {
          interval: 0,
          rotate: 40,
          textStyle: {
            fontSize: 10
          }
        }
      },
      yAxis:{},
      series: [
        {
          type: "bar",
          encode: {
            x: "time_period",
            y: "job_count"
          },
          itemStyle: {
            color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [
          {
            offset: 0,
            color: 'rgb(55, 162, 255)'
          },
          {
            offset: 1,
            color: 'rgb(116, 21, 219)'
          }
        ])

          },
          clip: false,
          symbol: "none",
        },
      ],
      animationDuration: 5000,
    });
  },
};
</script>

<style scoped>
.chart {
  width: 100vw;
  height: 50vh;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 1s;
  animation-fill-mode: backwards;
}

.a {
  padding-top: 15vh;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 0.5s;
  animation-fill-mode: backwards;
}
</style>