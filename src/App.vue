<script setup>
import { RouterLink, RouterView } from 'vue-router'
import EnvironmentComponent from './components/environment/EnvironmentComponent.vue';
</script>

<template>
  <EnvironmentComponent />
  <header>
    <div class="wrapper">
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped lang="scss">
nav {
  a {
    &.router-link-active {
      border-bottom: 1px solid;
      border-color: hsla(160, 100%, 37%, 1);
    }
  }
}
</style>
