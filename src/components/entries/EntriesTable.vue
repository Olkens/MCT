<template>
  <div class="flex flex-col items-center justify-center h-full">
    <ul v-for="entry in entries" :key="entry.id">
      <ListItem :entry="entry"/>
    </ul>
    <button @click="add">hehe</button>
  </div>
</template>
<script setup>
import supabase from "../../services/supabase.js";
import {onMounted, ref} from "vue";
import ListItem from "./ListItem.vue";

const entries = ref([])

async function fetchEntries() {
  try {
    let {data: data, error} = await supabase
        .from('test')
        .select('*')
    entries.value = data
  } catch (error) {
    console.log(error)
  }
}

onMounted(() => {
  fetchEntries()
})


const add = () => {
  entries.value.push({id: 5, date: 1, test: 'uwu'})
}
</script>

<style scoped>
ul {
  color: #fff;
  border: 1px solid #fff;
  border-radius: 15px;
  padding: 8px 12px;
}
</style>