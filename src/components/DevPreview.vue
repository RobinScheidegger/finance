<template>
  <PaymentOverview
    :paymentArray="[
      {
        type: 'payment',
        date: new Date('2021-11-01'),
        description: 'Essen in London',
        category: ['Essen'],
        amount: 30.5,
      },
      {
        type: 'payment',
        date: new Date('2021-11-01'),
        description: 'Neues Crash',
        category: ['Schlagzeug'],
        amount: 140.8,
      },
      {
        type: 'salary',
        date: new Date('2021-11-01'),
        description: 'Lohn',
        category: ['Lohn'],
        amount: 764,
      },
      {
        type: 'save-money',
        date: new Date('2021-11-01'),
        description: 'Sparen',
        category: ['Sparen'],
        amount: 400,
      },
    ]"
    :filterArray="[]"
    @clickedCard="(i) => test1(i)"
    @clickedCreateNew="test2()"
  >
  </PaymentOverview>
</template>

<script>
import PaymentOverview from "@/components/PaymentOverview.vue";
export default {
  name: "DevPreview",
  components: {
    PaymentOverview,
  },
  methods: {
    test1(index) {
      console.log("card ", index);
    },
    test2() {
      console.log("create new");
    },
  },
};
</script>
