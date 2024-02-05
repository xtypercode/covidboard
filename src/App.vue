<script lang="ts">
import Board from './components/Board.vue'

export default {
  components: {
    Board
  }
};
</script>

<template>
  <div>
    <main class="container">
      <Board />
    </main>
  </div>
</template>

<style scoped>
.logo {
  height: 1.5em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
