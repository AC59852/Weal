<template>
  <section class="patterns">

    <!-- Add chart time range buttons. -->
    <div>
      <button class="charts__button" @click="loadChart(1)">Weekly</button>
      <button class="charts__button" @click="loadChart(2)">Monthly</button>
      <button class="charts__button" @click="loadChart(3)">Yearly</button>
    </div>

    <!-- Add chart image or code, time allowing. -->
    <div class="chart__image">
      <img v-bind:src="charts[activeChart].imgSrc" v-bind:alt="charts[activeChart].imgAlt" v-bind:title="charts[activeChart].imgTitle" width="300">
    </div>

    <!-- Add list of Journal Entries (Daily Check-in input data). -->
    <div>
      <span>Daily Check-ins Journal Entries from this {{charts[activeChart].journalTime}}</span>
    </div>

  </section>
</template>

<script>
export default {
  data() {
    return {
      charts: [
        {
          id: 1, 
          imgSrc: '@/assets/PatternsCharts1.png', // Weekly Chart
          imgAlt: 'Weekly Chart',
          imgTitle: 'Weekly Chart',
          journalTime: 'Week',
        },

        {
          id: 2, 
          imgSrc: '@/assets/PatternsCharts2.png', // Monthly Chart
          imgAlt: 'Monthly Chart',
          imgTitle: 'Monthly Chart',
          journalTime: 'Month',
        },
      ],
    }
  },


  methods: {
    /*
    loadChart : function(chart) {
        //this.charts.shift();

        console.log(this.chartHidden);
        if (this.chartHidden) {
          this.chartHidden = false;
        } else {
          this.chartHidden = true;
        }
      }
      */
     loadChart(chartNum) {
        activeChart = chartNum; // Ex. If loadChart(1), then activeChart = 1
     }
    }, // End of methods.

    logChoice(event) {
      console.log(event.target.value);
    }

} // End of export default.
</script>

<style>

</style>