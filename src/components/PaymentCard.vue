<template>
  <div class="payment-card" @click="$emit('clickedCard')">
    <div class="payment-card__left">
      <div
        class="left__top"
        :class="{
          'subtitle-1': type === 'create-new',
          'subtitle-4': type === 'movement',
        }"
      >
        {{ contentTop }}
      </div>
      <div
        class="left__bottom subtitle-4"
        :class="{
          '--create': type === 'create-new',
          '--movement': type === 'movement',
        }"
      >
        {{ contentBottom }}
      </div>
    </div>
    <div class="payment-card__right">
      <IconCard
        :type="iconType"
        :size="iconSize"
        :opacity="iconOpacity"
        class="right__icon"
        :class="{
          '--create': type === 'create-new',
          '--movement': type === 'movement',
        }"
      />
      <div
        class="right__amount title-2"
        v-if="type === 'movement'"
        :class="{ '--light': movement?.type != 'payment' }"
      >
        CHF {{ movement?.amount?.toFixed(2) }}
      </div>
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
      default: 'movement'
    },
    movement: {
      type: Object,
      default: () => ({})
    }
  },

  computed: {
    iconType() {
      return this.type === 'create-new' ? "add-new" : this.movement?.type;
    },
    iconSize() {
      return this.type === 'movement' ? 24 : 32
    },
    iconOpacity() {
      return this.type === 'movement' ? 0.7 : 0.5
    },
    contentTop() {
      return this.type === 'create-new' ? "Neuen" : `${this.movement?.date?.getDate() < 10 ? 0 : ""}${this.movement?.date?.getDate()}.${this.movement?.date?.getMonth() + 1 < 10 ? 0 : ""}${this.movement?.date?.getMonth() + 1}.${this.movement?.date?.getFullYear()}`;
    },
    contentBottom() {
      return this.type === 'create-new' ? "Eintrag erstellen" : this.movement?.description;
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
  cursor: pointer;

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
    .left__bottom {
      &.--create {
        color: #999999;
      }
      &.--movement {
        margin-top: 7px;
      }
    }
  }

  &__right {
    margin-right: 20px;

    .right__icon {
      &.--create {
        margin: 24px 20px 24px 0px;
      }
      &.--movement {
        margin-top: 10px;
        display: flex;
        justify-content: flex-end;
      }
    }
    .right__amount {
      margin: 1px 0px 15px 0px;
      &.--light {
        color: #666666;
      }
    }
  }
}
</style>
