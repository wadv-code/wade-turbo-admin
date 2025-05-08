<script setup lang="ts">
import { useDark, useToggle } from '@vueuse/core';
import { NMenu, NSwitch } from 'naive-ui';
import type { MenuMixedOption } from 'naive-ui/es/menu/src/interface';

defineProps<{
  menuOptions: MenuMixedOption[];
}>();

const isDark = useDark();
const toggleDark = useToggle(isDark);
</script>
<template>
  <div style="display: flex;align-items: center;padding: 0 10px;">
    <n-menu mode="horizontal" size="small" :options="menuOptions" />
    <n-switch :value="isDark" @update:value="toggleDark" />
  </div>
</template>
