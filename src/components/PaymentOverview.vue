<template>
  <div class="payment-overview">
    <div class="payment-overview__cards">
      <div class="cards__create-new">
        <PaymentCard type="create-new" />
      </div>
      <div class="cards__payments">
        <div
          class="payments__payment"
          v-for="payment in paymentArray"
          :key="payment"
        >
          <PaymentCard
            type="movement"
            :movement="payment"
            class="payment__payment-card"
          />
        </div>
      </div>
    </div>
    <div class="payment-overview__amount">
      <div class="amount__text title-2">Ausgaben</div>
      <div class="amount__value">
        <div class="value__amount title-2">637.50</div>
        <div class="value__from subtitle-1">/ 764.30 CHF</div>
      </div>
    </div>
  </div>
</template>

<script lang="typescript">
import PaymentCard from "@/components/PaymentCard.vue";

export default {
  name: "PaymentOverview",
  components: {
    PaymentCard
  },
  props: {
    paymentArray: {
        type: Array,
        default: () => [
            {
                type: 'payment',
                date: new Date('2021-11-01'),
                description: 'Essen in London',
                category: ['Essen'],
                amount: 30.5,
            },
            {
                type: 'payment',
                date: new Date('2021-11-01'),
                description: 'Neues Crash',
                category: ['Schlagzeug'],
                amount: 140.8,
            },
            {
                type: 'salary',
                date: new Date('2021-11-01'),
                description: 'Lohn',
                category: ['Lohn'],
                amount: 764,
            },
            {
                type: 'save-money',
                date: new Date('2021-11-01'),
                description: 'Sparen',
                category: ['Sparen'],
                amount: 764,
            }
        ]
    },
    filterArray: {
        type: Array,
        default: () => ['Schlagzeug', 'Essen']
    }
  }
};
</script>

<style lang="scss">
.payment-overview {
  &__cards {
    .cards__create-new {
      margin-bottom: 20px;
    }
    .cards__payments {
      max-height: 300px;
      overflow: scroll;
      scrollbar-width: none;
      &::-webkit-scrollbar {
        display: none;
      }
      border-bottom: 1px solid #e1e1e1;

      .payment__payment-card {
        margin-bottom: 20px;
      }
    }
  }

  &__amount {
    margin-top: 20px;
    display: flex;
    justify-content: space-between;

    .amount__value {
      display: flex;
      gap: 4px;
    }
  }
}
</style>
