<template>
<ul>
  <ListItem v-for="entry in entries" :key="entry.id" entry-name="entry.test">
    {{entry.test}}
  </ListItem>
</ul>
  <button @click="add">hehe</button>
</template>
<script setup>
import supabase from "../../services/supabase.js";
import {onMounted, ref} from "vue";
import ListItem from "./ListItem.vue";

let {data: entries, error} = ref(await supabase
    .from('test')
    .select('test')
)

const add = () => {
  entries.push({id: 5, date: 1, test: 'uwu'})
  console.log(entries)
}
</script>