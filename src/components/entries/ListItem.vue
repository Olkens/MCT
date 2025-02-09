<template>
  <div>
    <span>{{ entry.id }} </span>
    <span>{{ entry.name }} </span>
    <span>{{ entry.amount }} </span>
    <span>{{entry.payments_left}}</span>
    <span>add</span>
    <span>delete</span>
  </div>
</template>

<script setup>
defineProps(['entry'])
</script>

<style scoped>
div {
  color: #fff;
}

span {
  padding: 8px 12px;

}

li {
  text-decoration: none;
  list-style: none;
}
</style>