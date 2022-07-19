<template>
  <div class="monthly-saving-card" @click="$emit('clickedCard')">
    <SavingCard
      :saving="saving"
      type="monthly-saving"
      class="monthly-saving-card__content"
    />
  </div>
</template>

<script lang="typescript">
import SavingCard from '@/components/SavingContent.vue'

export default {
  name: "MonthlySavingCard",
  components: {
    SavingCard,
  },
  props: {
    saving: {
        type: Object,
        default: () => ({})
    }
  }
};
</script>

<style lang="scss">
.monthly-saving-card {
  background-color: #ffffff;
  border: 1px solid #e1e1e1;
  border-radius: 12px;
  cursor: pointer;

  &__content {
    margin: 15px 15px 10px 15px;
  }
}
</style>
