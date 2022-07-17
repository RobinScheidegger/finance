<template>
  <PaymentOverview
    type="movement"
    :movement="{
      type: 'payment',
      date: new Date('2021-11-01'),
      description: 'Essen in London',
      category: ['Lohn', 'Sparen'],
      amount: 30.5,
    }"
    @clickedCard="test"
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
    test() {
      console.log("fisch");
    },
  },
};
</script>
