<template>
  <main>
    <div>Loading content from content/.gitbook</div>
    <div v-if="data">data: {{ data }}</div>
    <div v-if="error">error: {{ error }}</div>
  </main>
</template>

<script setup lang="ts">
const FILE_PATH = ".gitbook/test";

let data: any;
let error: any;

try {
  data = await queryContent(FILE_PATH).findOne();
} catch (e) {
  error = e;
}
</script>
