<script setup>
import Table from '@/components/Table.vue';
import { ref } from 'vue';

const pessoas = ref(JSON.parse(localStorage.getItem("pessoas")) || []);
</script>

<template>
  <main>
    <Table :pessoas="pessoas" />
  </main>
</template>