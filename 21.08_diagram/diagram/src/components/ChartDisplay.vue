<template>
    <div>
        <canvas ref="chartCanvas"></canvas>
    </div>
</template>

<script>
import Chart from 'chart.js/auto';

export default {
    props: ["chartLabels", "chartData"],
    mounted() {
        this.renderChart();
    },   
    methods: { 
        renderChart() {
            const ctx = this.$refs.chartCanvas.getContext("2d");
            new Chart(ctx, {
                type: 'pie',
                data: {
                    labels: this.chartLabels,
                    datasets: [
                        {
                            data: this.chartData,
                            backgroundColor: [
                                'red',
                                'blue',
                                'green',
                                'orange',
                                'purple',
                                'pink',
                            ],
                        },
                    ],
                },
                options: {
                    responsive: true,
                },
            });
        }
    }
};
</script>
