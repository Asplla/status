<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/Channel.vue'
</script>

<template>
  <header>
    <svg aria-hidden="true" viewBox="0 0 808 808" version="1.1" width="125" height="125" class="site-logo logo" data-view-component="true">
      <path xmlns="http://www.w3.org/2000/svg" d="M723.8,84.4C647.5,8.5,537.9,0,404,0C269.9,0,160.1,8.6,83.9,84.7S0,270.4,0,404.4S7.7,648,84,724.1  S269.9,808,404,808s243.8-7.7,320-83.9s84-185.8,84-319.8C808,270.2,800.2,160.5,723.8,84.4z M395.8,432.8  c-35.3,55.5-83.3,103.4-140,138.8c-18.9,11.4-41.6,11.4-60.6,1.3c-18.9-10.1-30.3-29-31.5-50.5c0-21.4,11.4-41.6,30.3-51.7  c29-17.7,55.5-40.4,77-66.9c-22.7-26.5-47.9-47.9-77-66.9c-29-16.4-37.8-53-21.4-80.7c16.4-27.7,54.2-36.6,82-20.2  c56.8,35.3,103.4,82,140,137.5C407.2,391.2,407.2,415.1,395.8,432.8z M596.4,555.2H452.6c-26.5,0-47.9-12.6-47.9-37.8  s21.4-37.8,47.9-37.8h143.8c26.5,0,47.9,12.6,47.9,37.8C644.3,542.5,622.9,555.2,596.4,555.2z"/>
    </svg>

    <div class="wrapper">
      <HelloWorld />
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
  margin-bottom: 2rem;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--weui-FG-0);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--weui-FG-3);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
    margin-bottom: 0;
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
