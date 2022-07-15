<template>
  <PaymentCard
    type="payment"
    :content="{
      top: '01.11.2021',
      bottom: 'Essen in London',
      price: -20.5,
    }"
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
};
</script>
