<template>
  <Header />

  <div class="w-full mx-auto my-4 p-4 border border-black rounded-md">
    <Balance />
    <IncomeExpense />
    <TransactionList />
    <AddTransaction />
  </div>
</template>

<script setup>
import Header from "./components/Header.vue";
import Balance from "./components/Balance.vue";
import IncomeExpense from "./components/IncomeExpense.vue";
import TransactionList from "./components/TransactionList.vue";
import AddTransaction from "./components/AddTransaction.vue";
</script>
