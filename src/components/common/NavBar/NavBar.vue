<template>
  
  <n-menu  v-model:value="activeKey" mode="horizontal" :options="menuOptions" />
</template>

<script lang="ts">
import { defineComponent, h, ref, Component } from 'vue'
import { NIcon } from 'naive-ui'
import type { MenuOption } from 'naive-ui'
import {
  BookOutline as BookIcon,
  ImagesOutline as ImageIcon,
  LibraryOutline as LibraryIcon,
  PencilOutline as  PencilIcon,
  ReaderOutline as ReaderIcon,
  ChatboxOutline as ChatboxIcon,
  AddOutline as AddIcon,
} from '@vicons/ionicons5'
function renderIcon (icon: Component) {
  return () => h(NIcon, null, { default: () => h(icon) })
}

const menuOptions: MenuOption[] = [
{
    label: 'MagicAI',
    key: 'logo',
    disabled:true
  },

{
    show:true
  },
  {
    show:true
  },
{
    label: '论文',
    key: 'paper',
    icon: renderIcon(LibraryIcon),
    
  },
  {
    label: '文案',
    key: 'artical',
    icon: renderIcon(BookIcon),
  },
  {
    label: '翻译',
    key: 'translate',
    icon: renderIcon(PencilIcon),
  },
  {
    label: '图像',
    key: 'image',
    icon: renderIcon(ImageIcon),
  },
  
  {
    label: '学习助手',
    key: 'study_assitant',
    icon: renderIcon(ReaderIcon),
  },
  {
    show:true
  },
  {
    show:true
  },
  {
    show:true
  },
  {
    show:true
  },
  {
    label: '添加',
    key: 'add',
    icon: renderIcon(AddIcon),
  },
  {
    label: '消息',
    key: 'chat',
    icon: renderIcon(ChatboxIcon),
  },
  
]

export default defineComponent({
  setup () {
    return {
      activeKey: ref<string | null>(null),
      menuOptions
    }
  }
})
</script>