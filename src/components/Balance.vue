<template>
  <h4 class="text-md text-center font-normal text-slate-500">
    Account Balance
  </h4>
  <h1 id="balance" class="font-bold text-4xl text-black text-center">
    Rp {{ total || "-" }}
  </h1>
</template>

<script setup>
const props = defineProps({
  total: {
    type: Number,
    required: true,
  },
});
</script>
