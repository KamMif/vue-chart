<template>
    <div :class="$style.chart__title">{{title}}</div>
    <div
        :class="$style.chat__container"
        :style="{ gridTemplateColumns: `${grid.map(({path}) => path).join(' ')}` }"
    >
      <div :class="$style.progress__container" :style="{ 'width': `${progress}%` }">
        <div :class="$style.dotted__item"/>
        <img src="../assets/arrow.svg" alt="arrow" :class="$style.arrow__icon">
      </div>
      <div
          v-for="({ color }, index) in grid"
          :key="index"
          :class="$style.chart_block"
          :style="{
            backgroundColor: `${color}`,
          }"
      />
    </div>
    <div :class="$style.bottom_block__container">
      <div v-for="(text, index) in bottomBlock" :key="index">{{text}}</div>
    </div>
</template>

<script>
  export default {
    name: 'Chart',
    props: {
      title: String,
      progress: Number,
      grid: Array,
      bottomBlock: Array,
    },

  }
</script>

<style module>
  .chart__title {
    color: darkgray;
    display: flex;
    align-items: center;
    font-size: 12px;
  }
  .chat__container {
    width: 100%;
    display: grid;
    grid-template-columns: 35% 25% 40%;
    height: 100%;
    position: relative;
    align-items: center;
  }
  .chart_block {
    height: 100%;
  }
  .chart_block:first-child {
    border-top-left-radius: 16px;
  }
  .progress__container {
    max-width: 100%;
    height: 100%;
    position: absolute;
    display: flex;
    justify-content: flex-start;
    align-items: center;
  }
  .arrow__icon {
    height: 64%;
    position: absolute;
    right: 0;
  }
  .dotted__item {
    width: 95%;
    height: 8%;
    background: url("../assets/dashed.svg") repeat-x;
  }
  .bottom_block__container {
    margin-top: 5px;
    padding: 0 5px 0 5px;
    display: flex;
    justify-content: space-between;
    font-size: 11px;
    color: darkgray;
  }
</style>