<template>
  <div class="monthly-saving-overview">
    <div
      class="monthly-saving-overview__card"
      v-for="saving in monthlySavings"
      :key="saving"
    >
      <MonthlySavingCard :saving="saving" />
    </div>
  </div>
</template>

<script lang="typescript">
import MonthlySavingCard from "@/components/MonthlySavingCard.vue";

export default {
  name: "MonthlySavingOverview",
  components: {
    MonthlySavingCard,
  },
  props: {
    monthlySavings: {
        type: Array,
        default: () => []
    }
  }
};
</script>

<style lang="scss">
.monthly-saving-overview {
  display: flex;
  flex-direction: column;
  gap: 20px;
}
</style>
