<script setup lang="ts">
import { NMenu } from 'naive-ui';
import type { MenuMixedOption } from 'naive-ui/es/menu/src/interface';
defineProps<{
  menuOptions: MenuMixedOption[];
}>();
</script>
<template>
  <n-menu :collapsed-width="64" :collapsed-icon-size="22" :options="menuOptions" />
</template>
