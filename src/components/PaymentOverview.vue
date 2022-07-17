<template>
  <div class="payment-overview">
    <div class="payment-overview__create-new">
      <PaymentCard type="create-new" />
    </div>
    <div class="payment-overview__payments">
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
  &__create-new {
    margin-bottom: 20px;
  }

  &__payments {
    .payment__payment-card {
      margin-bottom: 20px;
    }
  }
}
</style>
