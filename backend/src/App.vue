<script setup lang="ts">
import { useDark } from '@vueuse/core';
import { NConfigProvider, darkTheme } from 'naive-ui';
import LayoutView from './layouts/LayoutView.vue';

const isDark = useDark();
</script>
<template>
  <n-config-provider :theme="isDark ? darkTheme : null" :theme-overrides="{ common: { fontWeightStrong: '600' } }">
    <layout-view />
  </n-config-provider>
</template>
