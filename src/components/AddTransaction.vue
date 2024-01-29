<template>
  <div class="w-full mt-4">
    <h3 class="text-md text-center font-semibold text-black">
      Add new transaction
    </h3>
    <form id="form" @submit.prevent="onSubmit">
      <div class="flex flex-col items-start gap-2">
        <label for="text" class="text-slate-500">Title</label>
        <input
          type="text"
          id="text"
          placeholder="Enter text..."
          v-model="text"
          class="w-full p-3 rounded-md shadow-md"
        />
      </div>
      <div class="flex flex-col items-start gap-2 mt-2">
        <label for="amount" class="text-slate-500"
          >Amount <br />
          (negative - expense, positive - income)</label
        >
        <input
          type="number"
          id="amount"
          placeholder="Enter amount..."
          v-model="amount"
          class="w-full p-3 rounded-md shadow-md"
        />
      </div>
      <button
        class="w-full mt-3 bg-blue-600 hover:bg-blue-500 text-white py-2 rounded-md shadow-md"
      >
        Add transaction
      </button>
    </form>
  </div>
</template>

<script setup>
import { useToast } from "vue-toastification";
import { ref } from "vue";

const text = ref("");
const amount = ref("");
const toast = useToast();

const emit = defineEmits(["transactionSubmitted"]);

const onSubmit = () => {
  if (!text.value || !amount.value) {
    // Display a toast error message if either field is empty
    toast.error("Both fields must be filled.");
    return;
  }

  const transactionData = {
    text: text.value,
    amount: parseFloat(amount.value),
  };

  emit("transactionSubmitted", transactionData);

  // Clear form fields
  text.value = "";
  amount.value = "";
};
</script>
