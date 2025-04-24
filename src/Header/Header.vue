<script setup>
import LogoBarVue from "./LogoBar.vue";
import TopBarVue from "./TopBar.vue";
import HeaderMenu from "./HeaderMenu.vue";
</script>

<style scoped>
</style>

<template>
  <div style="border-bottom: 1px solid #d9d9d9">
    <TopBarVue />
    <div class="gridOn">
      <LogoBarVue />
      <HeaderMenu />
    </div>
  </div>
</template>