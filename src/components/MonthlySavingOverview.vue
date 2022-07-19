<template>
  <div class="monthly-saving-overview">
    <div class="monthly-saving-overview__card">
      <MonthlySavingCard />
    </div>
  </div>
</template>

<script lang="typescript">
import MonthlySavingCard from "@/components/MonthlySavingCard.vue";

export default {
  name: "MonthlySavingCard",
  components: {
    MonthlySavingCard,
  },
  props: {
    saving: {
        type: Object,
        default: () => ({})
    }
  }
};
</script>

<style lang="scss"></style>
