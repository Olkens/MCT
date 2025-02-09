<script setup async>
import EntriesTable from "./components/entries/EntriesTable.vue";

</script>

<template>
  <Suspense>
    <EntriesTable></EntriesTable>
  </Suspense>
</template>

<style scoped>
body {
  background: #000;
}
</style>
