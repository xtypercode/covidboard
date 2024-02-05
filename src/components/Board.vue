<script lang="ts">
import axios from 'axios';
import Chart from 'chart.js/auto'

export default {
  data() {
    return {
      states: [],
    }
  },
  mounted() {
    axios.get('https://covid19-brazil-api.now.sh/api/report/v1')
      .then(response => {
        this.states = response.data.data;
        
        const chartCanvas = this.$refs.chartCanvas;
        new Chart(
          chartCanvas,
          {
            type: 'bar',
            data: {
              labels: this.states.map(state => state.state),
              datasets: [
                {
                  label: 'Covid - Casos confirmados',
                  data: this.states.map(state => state.cases)
                }
              ]
            }
          }
        );        
      })
      .catch(error => {
        console.error('Erro ao obter dados:', error);
      });
  }
};
</script>

<template>
<div class="container flex flex-col gap-5">
  <canvas ref="chartCanvas">
  </canvas>
</div>
</template> 

<style scoped>
</style>
