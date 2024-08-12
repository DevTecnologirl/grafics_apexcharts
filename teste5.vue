<!-- <template>
    <div>
      <BarChart />
    </div>
  </template>
  
  <script setup>
  import BarChart from '~/components/BarChart.vue';
  </script> -->
  
  <!-- <template>
    <div>
      <BarChart />
    </div>
  </template>
  
  <script>
  import BarChart from '~/components/BarChart.vue';
  
  export default {
    components: {
        BarChart
    }
  }
  </script>  -->

<template>
    <div>
      <LineChartClient/>
    </div>
  </template>
  
  <script>
  import LineChartClient from '~/components/LineChart.client.vue'
  
  export default {
    components: {
        LineChartClient
    }
  }
  </script>
  