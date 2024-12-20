<script setup lang="ts">
import { RouterView } from 'vue-router'
</script>

<template>
  <div class="app-container">
    <RouterView />
  </div>
</template>

<style>
/* 重置默认样式 */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

:root {
  --mint-green: #a8e6cf;
  --ocean-blue: #1e90ff;
}

html,
body,
#app {
  height: 100%;
  width: 100%;
  padding: 0px;
  overflow: hidden;
}

.app-container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, var(--mint-green) 0%, var(--ocean-blue) 100%);
}
</style>
