<template>
  <div id="chart">
    <apexchart type="line" height="350" :options="chartOptions" :series="series" />
  </div>
</template>

<script>
import VueApexCharts from 'vue3-apexcharts'

export default {
  components: {
    apexchart: VueApexCharts,
  },
  data() {
    return {
      series: [
        {
          name: 'Volume',
          color: '#1A3B47',
          type: 'column',
          data: [1.4, 2, 2.0, 1.5, 2.5, 2.8, 200.8, 4.6, 1.4, 2, 2.0, 1.5, 2.5, 2.8, 3.8, 4.6, 1.4, 2, 2.0, 1.5, 2.5, 2.8, 3.8, 4.9,],
        },
        {
          name: 'Média',
          color: '#299D91',
          type: 'column',
          data: [1, 3, 3.1, 4, 4.1, 4.9, 6.5, 8.5, 100.1, 3, 3.1, 4, 4.1, 4.9, 6.5, 8.5, 1.1, 3, 3.1, 4, 4.1, 4.9, 6.5, 8.5],
        },
        {
          name: 'Impacto',
          color: '#D23232',
          type: 'line',
          data: [20, 29, 37, 36, 44, 45, 50, 58, 20, 29, 37, 36, 44, 45, 50, 58, 20, 29, 37, 36, 44, 45, 50, 58,],
        },
      ],
      chartOptions: {
        chart: {
          height: 250,
          type: 'line',
          stacked: false,
        },
        dataLabels: { //mostrar valores da linha
          enabled: false,
        },
        stroke: { //ajuste de linha
          width: [1, 1, 2],
          dashArray: [0, 0, 5],
        },
        title: { //inspiração para label de volume media e impacto no topo
          text: '',
          align: 'left',
          offsetX: 100,
        },

        xaxis: {
          categories: ['00:00:00', '00:01:00', '00:02:00', '00:03:00', '00:04:00', '00:05:00', '00:06:00', '00:07:00', '00:08:00', '00:09:00', '00:10:00', '00:11:00', '00:12:00', '00:13:00', '00:14:00', '00:15:00', '00:16:00', '00:17:00', '00:18:00', '00:19:00', '00:20:00', '00:21:00', '00:22:00', '00:23:00'],
          "labels": {
            "rotate": -90,
            "rotateAlways": true,
            "trim": true,
            "style": {
              "colors": "#1A3B47", "fontSize": "12px",
              "fontWeight": 500
            }
          },
          axisTicks: {
            show: false, // Remover ticks
          },
          axisBorder: {
            show: false, // Remover borda
          },

        },

        yaxis: [
          {
            "tickAmount": 4,
            "max": 200,
            "min": 0,
            seriesName: 'LabelX',
            axisTicks: {
              show: false,
            },
            axisBorder: {
              show: false,
              color: '#D23232',
            },
            labels: {
              formatter: function (value) {
                return value.toFixed(0); // Formata para valores inteiros
              },
              style: {
                colors: '#9F9F9F',
              },
            },
            title: {
              text: '',
              style: {
                color: '#D23232',

              },
            },
            tooltip: {
              enabled: true,
            },
          },
        ],


        tooltip: {
          fixed: {
            enabled: true,
            position: 'topLeft', // topRight, topLeft, bottomRight, bottomLeft
            offsetY: 100,
            offsetX: 60,
          },
        },
        legend: {
          horizontalAlign: 'left',
          offsetX: 90,
          "position": "top",
          "horizontalAlign": "left",
          "fontSize": 14,
          "offsetX": -10,
          "offsetY": 10,
          "markers": {
            "size": 7,
            "shape": "square"
          },
          "itemMargin": {
            "vertical": 0
          }

        },
      },
    };
  },
};
</script>

<style>
#chart {
  width: 715px;
  background-color: #ffffff;
  height: 316%;
  margin: 100px auto;
}
</style>
