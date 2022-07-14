<template>
  <div class="payment-card">
    <CardBorder>
      <div class="payment-card__content">
        <div class="content__left">
          <div
            class="left__top"
            :class="{
              payment: type === 'payment',
              'create-new': type === 'create-new',
              'subtitle-1': type === 'create-new',
              'subtitle-4': type === 'payment',
            }"
          >
            01.11.2021
          </div>
          <div
            class="left__bottom subtitle-4"
            :class="{
              payment: type === 'payment',
              'create-new': type === 'create-new',
            }"
          >
            Essen in London
          </div>
        </div>
        <div class="content__right">
          <div class="right__amount title-2" v-if="type === 'payment'">
            CHF 32.00
          </div>
          <div class="right__icon">
            <IconCard icon="add-new" v-if="type === 'create-new'" />
          </div>
        </div>
      </div>
    </CardBorder>
  </div>
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
    type: {
        type: String,
        // payment / create-new
        default: 'payment',
    }
  }
};
</script>

<style lang="scss">
.payment-card {
  &__content {
    margin: 15px 20px;
    display: flex;
    justify-content: space-between;
    .content__left {
      .left__top {
        &.payment {
          color: #cccccc;
        }
        &.create-new {
          color: #999999;
        }
      }
      .left__bottom {
        &.payment {
          margin-top: 7px;
        }
        &.create-new {
          color: #999999;
        }
      }
    }
    .content__right {
      .right__amount {
        margin-top: 20px;
      }
      .right__icon {
        margin-right: 20px;
      }
    }
  }
}
</style>
