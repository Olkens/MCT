<template>
<ul>
  <li v-for="entry in entries">
    {{entry.test}}
  </li>
</ul>
  <button @click="add">hehe</button>
</template>
<script setup>
import supabase from "../../services/supabase.js";
import {onMounted, ref} from "vue";

let {data: entries, error} = ref(await supabase
    .from('test')
    .select('test')
)

const add = () => {
  entries.push({id: 5, date: 1, test: 'uwu'})
  console.log(entries)
}
</script>