<template>
    <div>
      <div v-for="(data, index) in chartData" :key="index">
        <input v-model.number="data.value" type="number" :placeholder="'Value ' + (index + 1)" />
      </div>
      <button @click="addDataPoint">Add Data Point</button>
      <button @click="generateChart">Generate Chart</button>
    </div> 
  </template>
  
  <script>
  export default {
    data() {
      return {
        chartData: [{ label: "", value: 0 }],
        newValue: 0,
      };
    },
    methods: {
      addDataPoint() {
        this.chartData.push({ label: "", value: this.newValue }); 
      },
      generateChart() {
        const labels = this.chartData.map((data) => data.label);
        const values = this.chartData.map((data) => data.value);
  
        this.$emit("generate-chart", labels, values);
      },
    },
  };
  </script>
  