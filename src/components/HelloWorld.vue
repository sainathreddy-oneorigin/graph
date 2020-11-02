<template>
  <div>
    <div class="chart-wrapper">
      <apexchart width="800" type="bar" :options="options" :series="series">
      </apexchart>
    </div>
  </div>
</template>
  
<script>
export default {
  name: "HelloWorld",
  data: () => ({
    options: {
      chart: {
        id: "vuechart-example",
      },
      xaxis: {
        categories: [
          "Current Grade",
          "Grade",
          "Course Readiness Quiz",
          "Content Mastery 1",
          "Content Mastery 2",
          "Content Mastery 3",
          "Content Mastery 4",
          "Content Mastery 5",
          "Content Mastery 6",
          "Content Mastery 7",
          "Content Mastery 8",
          "Content Mastery 9",
        ],
      },
      title: {
        text: "Students Score",
        align: "center",
        style: {
          fontSize: "20px",
        },
      },
      colors: [
        function ({ data }) {
          if (data < 55) {
            return "#7E36AF";
          } else {
            return "#D9534F";
          }
        },
      ],
      subtitle: {
        text: undefined,
        align: "left",
        margin: 10,
        offsetX: 0,
        offsetY: 0,
        floating: false,
        style: {
          fontSize: "12px",
          fontWeight: "normal",
          fontFamily: undefined,
        },
      },
    },
    series: [
      {
        name: "Score",
        data: [0.93, 0.24, 1, 1, 1, 1, 1, 1, 1, 1, 0.085714286, 1],
      },
    ],
  }),
};
</script>

<style scoped>
div.chart-wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>