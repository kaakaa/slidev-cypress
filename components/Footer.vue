<script setup lang="ts">
import { computed, getCurrentInstance } from "vue";

const vm = getCurrentInstance();
const progress = computed(() => {
  const nav = vm.appContext.config.globalProperties.$slidev!.nav;
  return {
    width: Math.ceil(100 * ((nav.currentPage - 1) / (nav.total - 1))) + "%",
    height: "5px",
  };
});
</script>
<template>
  <div style="width: 100%; height: 5px">
    <div class="bg-rose-500" :style="progress"></div>
  </div>
</template>
