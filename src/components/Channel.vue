<template>
  <div class="greetings">
    <h1 class="blue site-title">System Status</h1>
    <div class="legend">
      <div class="legend-item status-icon unknow-icon">未知</div>
      <div class="legend-item status-icon success-icon">可用</div>
      <div class="legend-item status-icon paused-icon">维护中</div>
      <div class="legend-item status-icon fail-icon">不可用</div>
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
