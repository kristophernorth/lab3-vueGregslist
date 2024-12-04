<script setup>

import { AppState } from '@/AppState';
import { computed } from 'vue';

const account = computed(() => AppState.account)

</script>


<template>
  <h1>House Form</h1>
</template>


<style lang="scss" scoped>

</style>