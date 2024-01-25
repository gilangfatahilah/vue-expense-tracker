<template>
  <div class="flex justify-between items-center gap-4 mt-6">
    <div
      class="flex justify-evenly items-center gap-3 bg-[#00A86B] rounded-3xl p-4"
    >
      <img src="../assets/icons/income.svg" alt="income image" />
      <div>
        <h4 class="text-white font-thin">Income</h4>
        <p id="money-plus" class="text-xl font-bold text-white">
          Rp {{ income || "-" }}
        </p>
      </div>
    </div>
    <div
      class="flex justify-evenly items-center gap-3 bg-[#FD3C4A] rounded-3xl p-4"
    >
      <img src="../assets/icons/expense.svg" alt="expense image" />
      <div>
        <h4 class="text-white font-thin">Expense</h4>
        <p id="money-minus" class="text-xl font-bold text-white">
          Rp {{ income || "-" }}
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  income: {
    type: Number,
    required: true,
  },
  expenses: {
    type: Number,
    required: true,
  },
});
</script>
