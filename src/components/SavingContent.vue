<template>
  <div
    class="saving-content"
    :class="{
      '--big': type === 'monthly-saving',
      '--small': type === 'saving-account',
    }"
  >
    <div class="content__text subtitle-3">{{ saving.description }}</div>
    <div class="content__amount">
      <div class="amount__current subtitle-2">
        CHF {{ saving.savedAmount?.toFixed(2) }}
      </div>
      <div class="amount__divider subtitle-2">/</div>
      <div class="amount__monthly title-3">
        CHF {{ saving.fixedValue?.toFixed(2) }}
      </div>
    </div>
  </div>
</template>

<script lang="typescript">
export default {
  name: "SavingContent",
  props: {
    type: {
        type: String,
        default: 'monthly-saving',
    },
    saving: {
        type: Object,
        default: () => ({})
    }
  }
};
</script>

<style lang="scss">
.saving-content {
  display: flex;
  flex-direction: column;
  &.--small {
    gap: 10px;
  }
  &.--big {
    gap: 16px;
  }

  .content__text {
    color: #333333;
  }

  .content__amount {
    display: flex;
    justify-content: space-between;
  }
}
</style>
