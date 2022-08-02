<template>
  <el-header>
    <el-menu
      :default-active="activeIndex"
      class="sg-header--menu"
      mode="horizontal"
      :ellipsis="false"
      @select="handleSelect"
    >
      <RouterLink to="/">
        <el-menu-item index="0">SG Forum</el-menu-item>
      </RouterLink>

      <div class="flex-grow" />
      <RouterLink to="/login">
        <el-menu-item index="1">Login</el-menu-item>
      </RouterLink>
      <RouterLink to="/signup">
        <el-menu-item index="2">SignUp</el-menu-item>
      </RouterLink>

      <!-- <el-sub-menu index="3">
        <template #title>Workspace</template>
        <el-menu-item index="3-1">item one</el-menu-item>
        <el-menu-item index="3-2">item two</el-menu-item>
        <el-menu-item index="3-3">item three</el-menu-item>
      </el-sub-menu> -->
    </el-menu>
  </el-header>
</template>

<script lang="ts" setup>
import { ref } from "vue";

const activeIndex = ref("0");
const handleSelect = (key: string, keyPath: string[]) => {
  console.log(key, keyPath);
};
</script>

<style>
.flex-grow {
  flex-grow: 1;
}
.sg-header--menu {
    width: 80vw;
}
</style>