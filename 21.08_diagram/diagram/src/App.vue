<template>
  <div>
    <data-input @generate-chart="updateChart" />
    <chart-display :chart-labels="chartLabels" :chart-data="chartData" />
  </div>
</template>

<script>
import DataInput from './components/DataInput.vue';
import ChartDisplay from './components/ChartDisplay.vue';

export default {
  components: {
    DataInput,
    ChartDisplay,
  },
  data() {
    return {
      chartLabels: [],
      chartData: [],
    };
  },
  methods: {
    updateChart(labels,data) {
      this.chartLabels = labels;
      this.chartData = data;
    }
  }
}


</script>

<style>

</style>
