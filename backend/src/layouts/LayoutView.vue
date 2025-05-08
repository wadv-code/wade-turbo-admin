<script setup lang="ts">
import { BookOutline, PersonOutline, WineOutline } from '@vicons/ionicons5';
import { NIcon, NLayout, NLayoutContent, NLayoutFooter, NLayoutHeader, NLayoutSider } from 'naive-ui';
import { type Component, h } from 'vue';
import LayoutContent from './components/LayoutContent.vue';
import LayoutFooter from './components/LayoutFooter.vue';
import LayoutHeader from './components/LayoutHeader.vue';
import LayoutSider from './components/LayoutSider.vue';

function renderIcon(icon: Component) {
  return () => h(NIcon, null, { default: () => h(icon) });
}

const menuOptions = [
  {
    label: '且听风吟',
    key: 'hear-the-wind-sing',
    icon: renderIcon(BookOutline),
  },
  {
    label: '1973年的弹珠玩具',
    key: 'pinball-1973',
    icon: renderIcon(BookOutline),
    children: [
      {
        label: '鼠',
        key: 'rat',
      },
    ],
  },
  {
    label: '寻羊冒险记',
    key: 'a-wild-sheep-chase',
    icon: renderIcon(BookOutline),
  },
  {
    label: '舞，舞，舞',
    key: 'dance-dance-dance',
    icon: renderIcon(BookOutline),
    children: [
      {
        type: 'group',
        label: '人物',
        key: 'people',
        children: [
          {
            label: '叙事者',
            key: 'narrator',
            icon: renderIcon(PersonOutline),
          },
          {
            label: '羊男',
            key: 'sheep-man',
            icon: renderIcon(PersonOutline),
          },
        ],
      },
      {
        label: '饮品',
        key: 'beverage',
        icon: renderIcon(WineOutline),
        children: [
          {
            label: '威士忌',
            key: 'whisky',
          },
        ],
      },
      {
        label: '食物',
        key: 'food',
        children: [
          {
            label: '三明治',
            key: 'sandwich',
          },
        ],
      },
      {
        label: '过去增多，未来减少',
        key: 'the-past-increases-the-future-recedes',
      },
    ],
  },
];
</script>
<template>
  <n-layout position="absolute">
    <n-layout-header bordered>
      <layout-header :menu-options="menuOptions" />
    </n-layout-header>
    <n-layout has-sider>
      <n-layout-sider bordered show-trigger collapse-mode="width" :collapsed-width="64" :width="220"
        :native-scrollbar="false">
        <layout-sider :menu-options="menuOptions" />
      </n-layout-sider>
      <n-layout-content :native-scrollbar="false">
        <layout-content />
      </n-layout-content>
    </n-layout>
    <n-layout-footer bordered>
      <layout-footer />
    </n-layout-footer>
  </n-layout>
</template>
