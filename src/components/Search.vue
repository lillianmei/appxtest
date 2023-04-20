<script setup lang="ts">
import { ref } from 'vue'

const selectValue = ref('HR Announcement')

const options = [
  {
    value: 'HR Announcement',
    label: 'HR Announcement',
  },
  {
    value: 'News',
    label: 'News',
  },
  {
    value: 'All',
    label: 'All',
  },
]
</script>

<template>
  <el-row class="search">
    <el-col :span="5">
      <label for="Category">Category</label>
      <el-select class="m-2" placeholder="Select" size="large" v-model="selectValue">
        <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value" />
      </el-select>
    </el-col>
    <el-col :span="5">
      <label for="Subtitle">Subtitle</label>
      <el-input class="w-50 m-2" size="large" />
    </el-col>
    <button>Search</button>
  </el-row>
</template>

<style scoped lang="scss">
.search {
  align-items: flex-end;
  padding: 16px;
  background-color: #fff;
  label {
    display: block;
    font-size: .8rem;
    color: #737791;
    margin-bottom: 6px;
  }

  .el-col {
    margin-right: 10px;
  }

  .el-select {
    width: 100%;
  }

  button {
    height: 40px;
    background-color:#F2F2F7;
    color: #32395F;
    border:none;
    padding: 0 16px;
    font-size: 18px;
    border-radius: 8px;
  }
}</style>
