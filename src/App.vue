<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
<div class="nav">
<RouterLink class="link" to="/">Home</RouterLink>
<RouterLink class="link" to="/about">About</RouterLink>
</div>
<RouterView />
</template>

<style lang="scss">
.nav {
  display: flex;
  align-items: center;
  justify-content: space-around;
  background-color: rgb(43, 41, 41);
  width: 100vw;
  height: 2rem;

  .link {
    text-decoration: none;
    color: white;

    &:visited {
      color: white
    }
  }
}
</style>
