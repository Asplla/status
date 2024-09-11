<template>
  <div class="greetings">
    <h1 class="blue site-title">wxhub Status</h1>
    <div class="legend">
      <div class="legend-item">
        <i class="status-dot unknow-icon"></i>
        <span>未知</span>
      </div>
      <div class="legend-item">
        <i class="status-dot success-icon"></i>
        <span>可用</span>
      </div>
      <div class="legend-item">
        <i class="status-dot paused-icon"></i>
        <span>维护中</span>
      </div>
      <div class="legend-item">
        <i class="status-dot fail-icon"></i>
        <span>不可用</span>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">

</script>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}
.site-title {
  padding: 0;
}
.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
