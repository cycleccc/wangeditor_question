<template>
  <div class="common-layout">
    <el-container>
      <el-header width="100%">
        <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" :router="true"
          @select="handleSelect">
          <el-menu-item v-for="item in menus" :key="item.path" :index="item.path">
            {{ item.name }}
          </el-menu-item>
        </el-menu>
      </el-header>
      <el-main>
        <el-card>
          <router-view />
        </el-card>
      </el-main>
    </el-container>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const menus = ref([
  { path: '/questionPage', name: '复现问题' },
  { path: '/normal', name: '正常' },
])

const activeIndex = ref('/questionPage')
const handleSelect = (key: string, keyPath: string[]) => {
  activeIndex.value = key;
}
</script>

<style scoped></style>
