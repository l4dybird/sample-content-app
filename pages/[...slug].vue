<script setup lang="ts">
const route = useRoute();
const { data } = await useAsyncData('page-data', () => queryContent().find());
const page = data.value.filter((x) => x._path === route.fullPath)[0];
</script>


<template>
  <main>
    <ContentDoc :value="page"/>
  </main>
</template>