<script setup>
import supabase from "../services/supabase.js";
import {ref} from "vue";

let {data: test, error} = await supabase
    .from('test')
    .select('test')

const heh = ref(test)
const chuj = ref(0)
console.log(heh)

console.log(heh.value)

</script>

<template>
  <div>
    <div>kek</div>
    {{ heh }}
    {{ chuj }}
  </div>
</template>