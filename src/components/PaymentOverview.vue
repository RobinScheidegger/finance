<template>
  <div class="payment-overview">
    <div class="payment-overview__cards">
      <div class="cards__create-new" v-if="filterArray?.length === 0">
        <PaymentCard
          type="create-new"
          @clickedCard="$emit('clickedCreateNew')"
        />
      </div>
      <div class="cards__payments">
        <div
          class="payments__payment"
          v-for="(payment, index) in paymentArray"
          :key="payment"
        >
          <PaymentCard
            type="movement"
            :movement="payment"
            class="payment__payment-card"
            v-if="filter(payment.category) === true"
            @clickedCard="$emit('clickedPaymentCard', index)"
          />
        </div>
      </div>
    </div>
    <div class="payment-overview__amount">
      <div class="amount__text title-2">Ausgaben</div>
      <div class="amount__value">
        <div class="value__amount title-2">
          {{ calculateAmount()?.toFixed(2) }}
        </div>
        <div class="value__from subtitle-1" v-if="filterArray.length === 0">
          / {{ getSalary()?.toFixed(2) }}
        </div>
        <div
          class="value__chf"
          :class="{
            'subtitle-1': filterArray.length === 0,
            'title-2': filterArray.length > 0,
          }"
        >
          CHF
        </div>
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
        default: () => []
    },
    filterArray: {
        type: Array,
        default: () => []
    }
  },
  methods: {
    filter(allItems) {
        if (this.filterArray?.length === 0) return true;
        else return this.filterArray?.some(r=> allItems.includes(r))
    },
    calculateAmount() {
      let amountSumm = 0;
      for(let i = 0; i < this.paymentArray.length; i++) {
        if (this.filterArray?.length === 0 && this.paymentArray[i].type != 'salary') {
          amountSumm = amountSumm + this.paymentArray[i].amount;
        }
        else if (this.filterArray?.some(r=> this.paymentArray[i].category.includes(r)) === true) {
          amountSumm = amountSumm + this.paymentArray[i].amount;
        }
      }
      return amountSumm;
    },
    getSalary() {
      let salarySumm = 0;
      for(let i = 0; i < this.paymentArray.length; i++) {
        if (this.paymentArray[i].type === 'salary') salarySumm = salarySumm + this.paymentArray[i].amount;
      }
      return salarySumm;
    }
  }
};
</script>

<style lang="scss">
.payment-overview {
  &__cards {
    max-height: 550px;
    overflow: scroll;
    scrollbar-width: none;
    &::-webkit-scrollbar {
      display: none;
    }
    .cards__create-new {
      margin-bottom: 20px;
    }
    .cards__payments {
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
