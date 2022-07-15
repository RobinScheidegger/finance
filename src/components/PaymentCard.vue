<template>
  <div class="payment-card">
    <div class="payment-card__left">
      <div
        class="left__top"
        :class="{
          'subtitle-1': type === 'create-new',
          'subtitle-4': type === 'movement',
        }"
      >
        Lorem ipsum
      </div>
      <div class="left__bottom">Lorem ipsum dolor si amet</div>
    </div>
    <div class="payment-card__right">
      <IconCard />
      <div class="right__amount">CHF 30.50</div>
    </div>
  </div>
</template>

<script lang="typescript">
import IconCard from "@/components/IconCard.vue";

export default {
  name: "PaymentCard",
  components: {
    IconCard
  },
  props: {
    type: {
      type: String,
      // options) movement / create-new
      default: 'movement'
    },
    movement: {
      type: Object,
      default: () => ({
        // options) payment / save-money / salary
        type: 'payment',
        date: new Date("2021-11-01"),
        description: 'Essen in London',
        category: ['Lohn', 'Sparen'],
        amount: 30.50
      })
    }
  }
};
</script>

<style lang="scss">
.payment-card {
  background-color: #ffffff;
  border: 1px solid #e1e1e1;
  border-radius: 12px;

  display: flex;
  justify-content: space-between;

  &__left {
    display: flex;
    flex-direction: column;
    margin: 15px 0px 0px 20px;

    .left__top {
      &.subtitle-1 {
        color: #999999;
      }
      &.subtitle-4 {
        color: #cccccc;
      }
    }
  }

  &__right {
    background-color: orange;
  }
}
</style>
