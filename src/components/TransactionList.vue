<template>
  <div class="mt-6">
    <h3 class="text-md text-center font-semibold text-black">
      Recent Transaction
    </h3>
    <ul id="list" class="list">
      <li
        v-for="transaction in transactions"
        :key="transaction.id"
        :class="transaction.amount < 0 ? 'minus' : 'plus'"
      >
        {{ transaction.text }} <span>${{ transaction.amount }}</span
        ><button class="delete-btn" @click="deleteTransaction(transaction.id)">
          x
        </button>
      </li>
    </ul>
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
