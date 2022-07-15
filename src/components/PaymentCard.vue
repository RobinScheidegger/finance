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
            {{ content.top }}
          </div>
          <div
            class="left__bottom subtitle-4"
            :class="{
              payment: type === 'payment',
              'create-new': type === 'create-new',
            }"
          >
            {{ content.bottom }}
          </div>
        </div>
        <div class="content__right">
          <div class="right__amount title-2" v-if="type === 'payment'">
            {{ content.price }} CHF
          </div>
          <div class="right__icon" v-if="type === 'create-new'">
            <IconCard icon="add-new" />
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
    },
    content: {
      type: Object,
      default: () => ({
        top: '01.11.2021',
        bottom: 'Essen in London',
        price: 20.50
      })
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
      height: fit-content;
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
      max-height: fit-content;
      .right__amount {
        margin-top: 20px;
      }
      .right__icon {
        margin-right: 20px;
        margin-top: 9px;
        opacity: 0.5;
      }
    }
  }
}
</style>
