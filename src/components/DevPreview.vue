<template>
  <PaymentCard
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
  </PaymentCard>
</template>

<script>
import PaymentCard from "@/components/PaymentCard.vue";
export default {
  name: "DevPreview",
  components: {
    PaymentCard,
  },
  methods: {
    test() {
      console.log("fisch");
    },
  },
};
</script>
