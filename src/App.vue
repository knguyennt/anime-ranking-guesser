<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'

const test = 'something'
</script>

<template>
  <div>
    <RouterLink to="/">Main</RouterLink>
  </div>

  <RouterView />
</template>
