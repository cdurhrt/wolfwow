<script setup lang="ts">
import LayoutView from "./components/layout/LayoutView.vue";
import { NConfigProvider, darkTheme } from "naive-ui";
import { useThemeStore } from "./stores/theme";

const themeStore = useThemeStore();
</script>

<template>
  <n-config-provider :theme="themeStore.darkMode ? darkTheme : undefined">
    <div class="app-container">
      <layout-view>
        <RouterView />
      </layout-view>
    </div>
  </n-config-provider>
</template>

<style>
@import "@/assets/naive-overrides.css";

/* html,
body {
  margin: 0;
  padding: 0;
}
#app {
  max-width: 100vw;
  max-height: 100vh;
  overflow: hidden;
} */

.app-container {
  max-height: 100vh;
  overflow-y: hidden;
}
</style>
