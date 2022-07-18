<template>
  <div class="monthly-saving-card">
    <div class="monthly-saving-card__content">
      <div class="content__text subtitle-3">Schlagzeug Reparatur</div>
      <div class="content__amount">
        <div class="amount__current subtitle-2">CHF 150.00</div>
        <div class="amount__divider subtitle-2">/</div>
        <div class="amount__monthly title-3">CHF 100.00</div>
      </div>
    </div>
  </div>
</template>

<script lang="typescript">
export default {
  name: "MonthlySavingCard",
};
</script>

<style lang="scss">
.monthly-saving-card {
  background-color: #ffffff;
  border: 1px solid #e1e1e1;
  border-radius: 12px;

  &__content {
    margin: 15px 15px 10px 15px;
    display: flex;
    flex-direction: column;
    gap: 16px;

    .content__text {
      color: #333333;
    }

    .content__amount {
      display: flex;
      justify-content: space-between;
    }
  }
}
</style>
