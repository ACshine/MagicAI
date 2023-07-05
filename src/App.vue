<script setup lang="ts">
import { NConfigProvider } from 'naive-ui'
import { NaiveProvider } from '@/components/common'
import { useTheme } from '@/hooks/useTheme'
import { useLanguage } from '@/hooks/useLanguage'

import NavBar from '@/components/common/NavBar/NavBar.vue'

const { theme, themeOverrides } = useTheme()
const { language } = useLanguage()

</script>

<template>
    <NavBar></NavBar>
    <n-grid x-gap="12" :cols="4" >
    <n-gi span="3">
      <div class="light-green" >
        <NConfigProvider
    class="h-full"
    :theme="theme"
    :theme-overrides="themeOverrides"
    :locale="language"
  >
    <NaiveProvider>
      <RouterView />
    </NaiveProvider>
  </NConfigProvider>
      </div>
    </n-gi>
    <n-gi span="1">
      <div class="green">hh</div>
    </n-gi>
  </n-grid>
       

</template>
<style scoped>
.light-green {
  height: 670px;
}
.green {
  height: 670px;
  background-color: rgba(0, 128, 0, 0.24);
}
</style>