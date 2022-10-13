<template>
  <div>
    <q-card>
      <q-card-section class="text-h6">
        Gráfico Curva de Repasse {{ controladora.label }}
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
              <IEcharts />
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

import axios from "axios";

export default {
  name: "GraficoCurvaRepasse",
  props: {
    controladora: ref(0),
  },
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
            dataView: { show: false, readOnly: false },
            magicType: { show: false, type: ["line", "bar"] },
            restore: { show: false },
            saveAsImage: { show: false },
          },
        },
        legend: {
          data: ["uh", "Percentual"],
        },
        xAxis: [
          {
            type: "category",
            data: [],
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
            name: "Percentual",
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
              show: true,
              trigger: "item",
              //valueFormatter: function (value) {
              //  return value + " %";
              //},
            },
            data: [],
          },
          /*{
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
          },*/
        ],
      },
      bar_chart: null,
      vendas: null,
      acumulado: null,
      results: null,
    };
  },
  async created() {},
  async mounted() {
    console.log("controladora: ", this.controladora.value);
    let resp = await fetch(
      "/indices-operacionais/backend/get_controladora.php?CNPJ=" +
        cnpj.value +
        "&OPCAO=vendas"
    );
    let data = await resp.json();
    this.vendas = data;

    //for (let i = 0; i < this.vendas.length; i++) {
    //this.options.series[0].data.push(this.vendas[i].Acumulado * 100);
    //this.options.xAxis[0].data.push(this.vendas[i].ponto);
    this.options.series[0].data.push(0);
    this.options.xAxis[0].data.push(0);
    //console.log(this.vendas[i].Acumulado);
    //}
    console.log("acumuoado: ", this.options.series);

    //console.log("vendas", this.vendas.Acumulado.value);
    this.init();
  },
  watch: {
    "$q.dark.isActive": function () {
      this.init();
    },
    controladora: function (newVal, oldVal) {
      // watch it
      console.log("Prop changed: ", newVal, " | was: ", oldVal);
      this.fetchData(newVal);
      /*       let resp = fetch("http://localhost:3000/vendas?cnpj=" + newVal);
      let data = resp.json();
      this.vendas = data;
      this.options.series[0].data.splice;
      this.options.xAxis[0].data.splice;
      for (let i = 0; i < this.vendas.length; i++) {
        this.options.series[0].data.push(this.vendas[i].Acumulado * 100);
        this.options.xAxis[0].data.push(this.vendas[i].ponto);
      } */
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
    reload() {
      let barChart = document.getElementById("barChart");
      //echarts.dispose(barChart);

      this.bar_chart = echarts.init(barChart);
      this.bar_chart.setOption(this.options);
    },
    onResize() {
      if (this.bar_chart) {
        this.bar_chart.resize();
      }
    },
    async fetchData(cnpj) {
      let resp = await fetch(
        "/indices-operacionais/backend/get_controladora.php?CNPJ=" +
          cnpj.value +
          "&OPCAO=vendas"
      );
      let data = await resp.json();
      this.vendas = null;
      this.vendas = data;
      console.log(this.vendas);
      this.options.series[0].data = [];
      this.options.xAxis[0].data = [];
      for (let i = 0; i < this.vendas.length; i++) {
        this.options.series[0].data.push(this.vendas[i].Acumulado * 100);
        this.options.xAxis[0].data.push(this.vendas[i].ponto);
      }
      this.reload();
    },
  },
  components: {
    IEcharts,
  },
  computed: {},
};
</script>

<style scoped></style>
