<script setup lang="ts">
import { ArrowRight } from '@element-plus/icons-vue'

</script>

<template>
   <el-breadcrumb :separator-icon="ArrowRight" class="breadcrumb">
    <el-breadcrumb-item :to="{ path: '/' }">Home</el-breadcrumb-item>
    <el-breadcrumb-item>My Collection</el-breadcrumb-item>
  </el-breadcrumb>
</template>

<style scoped lang="scss">
  .breadcrumb{
    padding: 18px 8px;
  }
</style>
