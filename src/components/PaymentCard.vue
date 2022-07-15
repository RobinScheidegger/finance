<template>
  <div class="payment-card"></div>
</template>

<script lang="typescript">
import CardBorder from "@/components/CardBorder.vue";
import IconCard from "@/components/IconCard.vue";

export default {
  name: "PaymentCard",
  components: {
    CardBorder,
    IconCard
  },
  props: {
  }
};
</script>

<style lang="scss">
.payment-card {
}
</style>
