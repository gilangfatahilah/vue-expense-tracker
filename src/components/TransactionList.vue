<template>
  <div class="mt-6">
    <h3 class="text-md text-center font-semibold text-black">
      Recent Transaction
    </h3>
    <ul v-if="transactions.length !== 0" id="list" class="p-0 list-none mb-4">
      <li
        class="bg-white mt-4 relative flex justify-between p-3 rounded-md text-lg font-medium shadow-md"
        v-for="transaction in transactions"
        :key="transaction.id"
        :class="
          transaction.amount < 0
            ? ' border-r-4 border-[#c0392b]'
            : ' border-r-4 border-[#2ecc71]'
        "
      >
        {{ transaction.text }} <span>Rp {{ transaction.amount }}</span
        ><button class="delete-btn" @click="deleteTransaction(transaction.id)">
          x
        </button>
      </li>
    </ul>

    <p v-else class="text-slate-500 text-sm text-center mt-2 font-light">
      No Recent Transaction.
    </p>
  </div>
</template>

<script setup>
const props = defineProps({
  transactions: {
    type: Array,
    required: true,
  },
});

const emit = defineEmits(["transactionDeleted"]);

const deleteTransaction = (id) => {
  emit("transactionDeleted", id);
};
</script>
