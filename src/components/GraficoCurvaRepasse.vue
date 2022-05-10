<template>
  <div>
    <q-card>
      <q-card-section class="text-h6">
        Bar Chart
        <q-btn
          icon="fa fa-download"
          class="float-right"
          @click="SaveImage"
          flat
          dense
        >
          <q-tooltip>Download PNG</q-tooltip>
        </q-btn>
      </q-card-section>
      <q-card-section>
        <div ref="barchart" id="barChart" style="height: 500px">
          <q-card class="bg-white q-ml-sm shadow-11">
            <q-card-section class="q-pa-none map_height">
              <IEcharts :option="getBarChartOptions" :loading="loading" />
            </q-card-section>
          </q-card>
        </div>
      </q-card-section>
      <q-resize-observer @resize="onResize" />
    </q-card>
  </div>
</template>

<script>
import { markRaw, ref, onMounted } from "vue";
import { IEcharts } from "vue-echarts-v3/src/full.js";
import * as echarts from "echarts/lib/echarts";

export default {
  name: "GraficoCurvaRepasse",
  data() {
    return {
      model: false,
      options: {
        tooltip: {
          trigger: "axis",
          axisPointer: {
            type: "cross",
            crossStyle: {
              color: "#999",
            },
          },
        },
        toolbox: {
          feature: {
            dataView: { show: true, readOnly: false },
            magicType: { show: true, type: ["line", "bar"] },
            restore: { show: true },
            saveAsImage: { show: true },
          },
        },
        legend: {
          data: ["uh", "percent"],
        },
        xAxis: [
          {
            type: "category",
            data: [
              "1° Mês",
              "2° Mês",
              "3° Mês",
              "4° Mês",
              "5° Mês",
              "6° Mês",
              "7° Mês",
              "8° Mês",
              "9° Mês",
              "10° Mês",
              "11° Mês",
              "12° Mês",
            ],
            axisPointer: {
              type: "shadow",
            },
          },
        ],
        yAxis: [
          {
            type: "value",
            name: "uh",
            min: 0,
            max: 100,
            interval: 10,
            axisLabel: {
              formatter: "{value} %",
            },
          },
          {
            type: "value",
            name: "percent",
            min: 0,
            max: 100,
            interval: 10,
            axisLabel: {
              formatter: "{value} %",
            },
          },
        ],
        series: [
          {
            name: "Percentual UH Repassadas",
            type: "bar",
            tooltip: {
              valueFormatter: function (value) {
                return value + " %";
              },
            },
            data: [
              2.0, 4.9, 7.0, 23.2, 25.6, 36.7, 41.6, 46.2, 68.6, 72.0, 84.4,
              93.3,
            ],
          },
          {
            name: "Percentual de referência",
            type: "line",
            yAxisIndex: 1,
            tooltip: {
              valueFormatter: function (value) {
                return value + " %";
              },
            },
            data: [
              50.0, 50.0, 50.0, 50.0, 50.0, 50.0, 50.0, 50.0, 50.0, 50.0, 50.0,
              50.0,
            ],
          },
        ],
      },
      bar_chart: null,
    };
  },
  mounted() {
    this.init();
  },
  watch: {
    "$q.dark.isActive": function () {
      this.init();
    },
  },
  methods: {
    SaveImage() {
      const linkSource = this.bar_chart.getDataURL();
      const downloadLink = document.createElement("a");
      document.body.appendChild(downloadLink);
      downloadLink.href = linkSource;
      downloadLink.target = "_self";
      downloadLink.download = "BarChart.png";
      downloadLink.click();
    },
    init() {
      let barChart = document.getElementById("barChart");
      echarts.dispose(barChart);
      this.bar_chart = echarts.init(barChart);
      this.bar_chart.setOption(this.options);
    },
    onResize() {
      if (this.bar_chart) {
        this.bar_chart.resize();
      }
    },
  },
  components: {
    IEcharts,
  },
  computed: {
    getBarChartOptions() {
      let self = this;
      let filtered_data = this.data;

      return {
        grid: {
          bottom: "25%",
        },
        xAxis: {
          type: "category",
          axisLabel: {},
          nameLocation: "middle",
          nameGap: 78,
        },
        tooltip: {},
        dataset: {
          dimensions: ["product", "2015", "2016", "2017"],
          source: filtered_data,
        },
        yAxis: {
          type: "value",
          splitLine: {
            show: false,
          },
        },
        series: [{ type: "bar" }, { type: "bar" }, { type: "bar" }],
      };
    },
  },
};
</script>

<style scoped></style>
