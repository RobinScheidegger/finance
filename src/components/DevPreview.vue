<template>
  <MonthlySavingCard
    :saving="{
      description: 'Schlagzeug Reparatur',
      fixedValue: 100.0,
      savedAmount: 150.0,
    }"
    @clickedCard="test()"
  />
</template>

<script>
import MonthlySavingCard from "@/components/MonthlySavingCard.vue";
export default {
  name: "DevPreview",
  components: {
    MonthlySavingCard,
  },
  methods: {
    test() {
      console.log("click");
    },
  },
};
</script>
