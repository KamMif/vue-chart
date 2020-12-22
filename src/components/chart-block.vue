<template>
  <div :class="$style.container">
    <div :class="$style.header__container">
      <div :class="$style.header__title">Forecasts</div>
    </div>
    <div :class="$style.chart__container" v-for="(chartData, index) in chartsData" :key="index">
      <Chart
          :title="chartData.title"
          :progress="chartData.progress"
          :grid="chartData.grid"
          :bottomBlock="chartData.bottomBlock"
      />
    </div>
  </div>
</template>

<script>
import Chart from './chart'
export default {
  name: 'ChartBlock',
  props: {
    msg: String
  },
  components: {
    Chart
  },
  data: () => ({
    chartsData: [
      {
        title: 'Current Month',
        progress: 24,
        grid: [{color: 'darkblue', path: '25%'}, {color: 'blue', path: '35%'}, {color: 'lightblue', path: '40%'}],
        bottomBlock: ['$1.6', '$2.4']
      },
      {
        title: 'Current Quarter',
        progress: 66,
        grid: [{color: 'darkblue', path: '35%'}, {color: 'blue', path: '25%'}, {color: 'lightblue', path: '40%'}],
        bottomBlock: ['$2', '$3.4']
      }
    ]
  })
}
</script>

<style module>
  .container {
    height: 300px;
    width: 500px;
    box-shadow: 0px 5px 5px rgba(0, 0, 0, 0.1);
    border-radius: 16px;
    display: grid;
    grid-template-rows: 60px auto;
  }
  .header__container {
    border-bottom: 1px solid lightgray;
    display: flex;
    align-items: center;
  }
  .header__title {
    margin-left: 20px;
    text-transform: uppercase;
  }
  .chart__container {
    padding: 10px 30px 0 30px;
    display: grid;
    grid-template-rows: auto auto;
  }
</style>
