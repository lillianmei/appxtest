<template>
  <div class="about">
    <pagination/>
  </div>
</template>

<script setup>
// import { ref } from 'vue'
import  pagination  from '@/components/Pagination.vue'

components: {
  pagination
}

</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
