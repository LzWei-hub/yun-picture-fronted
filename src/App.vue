<template>
  <a-config-provider :locale="appLocale">
    <div id="app">
      <BasicLayout />
    </div>
  </a-config-provider>
</template>

<script setup lang="ts">
import BasicLayout from '@/layouts/BasicLayout.vue'
import { healthUsingGet } from '@/api/mainController'
import zhCN from 'ant-design-vue/es/locale/zh_CN'
import dayjs from "dayjs";
import 'dayjs/locale/zh-cn';

healthUsingGet().then((res) => {
  console.log(res)
})

// 设置 dayjs 默认语言为中文
dayjs.locale('zh-cn')

// 使用 Composition API 和 setup函数定义响应式数据
const appLocale = zhCN
</script>

<style scoped></style>
