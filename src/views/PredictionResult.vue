<template>
  <div class="pie-container">
    <apexchart
      type="pie"
      width="480"
      :options="chartOptions"
      :series="series"
    ></apexchart>
  </div>
</template>

<script>
import VueApexCharts from "vue3-apexcharts";
import axios from "axios";

export default {
  components: {
    apexchart: VueApexCharts,
  },
  data() {
    return {
      series: [44, 55],
      chartOptions: {
        chart: {
          width: 480,
          type: "pie",
        },
        labels: ["Theft", "Not Theft"],
        responsive: [
          {
            breakpoint: 480,
            options: {
              chart: {
                width: 200,
              },
              legend: {
                position: "bottom",
              },
            },
          },
        ],
      },
    };
  },
  methods: {
    updateChartData() {
      // const apiResponse = {
      //   message: "API response received and data deleted successfully",
      //   responseData: [80],
      // };

      // const responseData = apiResponse.responseData;
      // console.log("value" + responseData);
      // this.series = responseData;

      // const newData = [80];
      // const newLabels = ["Theft", "Not Theft"];

      // // Update the chart data.
      // this.series = newData;
      // this.chartOptions.labels = newLabels;

      axios
        .get("http://127.0.0.1:5000/api/theft/score")
        .then((response) => {
          // Assuming the API response is an array
          console.log(response.data.responseData[0]);

          const updateDataValue = response.data.responseData[0];

          if (updateDataValue === 0) {
          
           const newData = [85,15];
            const newLabels = ["Theft", "Not Theft"];

            // Update the chart data.
            this.series = newData;
            this.chartOptions.labels = newLabels;

          // const newData = [80];
            // const newLabels = ["Theft", "Not Theft"];

            // // // Update the chart data.
            // this.series = newData;
            // this.chartOptions.labels = newLabels;
          }else{
            const newData = [85,15];
            const newLabels = ["Theft", "Not Theft"];

            // Update the chart data.
            this.series = newData;
            this.chartOptions.labels = newLabels;
          }
          // this.series = response.data.responseData;
        })
        .catch((error) => {
          console.error("Error fetching data from the API:", error);
        });
    },
  },

  mounted() {
    this.updateChartData();
  },
};
</script>

<style>
@import "../css/PredicationResult.css";
</style>
