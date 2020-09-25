<script>
import { Bar } from 'vue-chartjs';

export default {
  extends: Bar,
  data() {
    return {
      chartData: {
        labels: ['01', '02', '03', '04', '05', '06', '07', '08', '09', '10', '11', '12'],
        datasets: [{
          label: 'Bar Chart',
          backgroundColor: 'rgba(0, 123, 255, 1)',
          pointBorderColor: '#2554FF',
          barPercentage: 0.2,
          barThickness: 10,
          data: [12, 19, 3, 5, 2, 3, 20, 3, 5, 6, 2, 1],
        }],
      },
      options: {
        scales: {
          yAxes: [{
            ticks: {
              beginAtZero: true,
            },
            gridLines: {
              display: true,
            },
          }],
          xAxes: [{
            categoryPercentage: 1.0,
            barPercentage: 1.0,
            ticks: {
              display: false,
            },
            gridLines: {
              display: false,
            },
          }],
        },
        legend: {
          boxWidth: 20,
          display: false,
        },
        responsive: true,
        maintainAspectRatio: false,
      },
    };
  },
  mounted() {
    this.renderChart(this.chartData, this.options);
  },
};
</script>
