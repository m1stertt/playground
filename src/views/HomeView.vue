<template>
  <div>
    <h1>Home Page</h1>
    <p>Welcome to the home page.</p>

    <select v-model="selectedChart">
      <option value="line">Line Chart</option>
      <option value="bar">Bar Chart</option>
      <option value="pie">Pie Chart</option>
    </select>

    <apexchart :options="chartOptions[selectedChart]" :series="chartSeries[selectedChart]"></apexchart>
  </div>
</template>

<script>
import { ref } from 'vue';
import VueApexCharts from 'vue-apexcharts';

export default {
  name: 'HomeView',
  components: {
    apexchart: VueApexCharts,
  },
  setup() {
    const selectedChart = ref('line');

    const chartOptions = {
      line: {
        chart: {
          type: 'line',
          height: 350
        },
        xaxis: {
          categories: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug']
        }
      },
      bar: {
        chart: {
          type: 'bar',
          height: 350
        },
        xaxis: {
          categories: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug']
        }
      },
      pie: {
        chart: {
          type: 'pie',
          height: 350
        },
        labels: ['Team A', 'Team B', 'Team C', 'Team D', 'Team E']
      }
    };

    const chartSeries = {
      line: [{
        name: "Line Dataset",
        data: [30, 40, 45, 50, 49, 60, 70, 91]
      }],
      bar: [{
        name: "Bar Dataset",
        data: [30, 40, 45, 50, 49, 60, 70, 91]
      }],
      pie: [44, 55, 41, 17, 15]
    };

    return { selectedChart, chartOptions, chartSeries };
  },
};
</script>