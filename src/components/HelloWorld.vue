<template>
  <p>
    ${{ bank.dollars }} = {{ bank.cents }}
    <button @click="bank.dollars++">Make more money</button>
  </p>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

class Bank {
  dollars: number;

  constructor() {
    this.dollars = 0;
  }

  get cents(): number {
    return this.dollars * 100;
  }
}

export default defineComponent({
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  data() {
    return {
      bank: {} as Bank,
    };
  },
  created() {
    this.bank = new Bank();
  },
});
</script>
