<template>
  <MonthlySavingOverview
    :monthlySavings="[
      {
        description: 'Schlagzeug Reparatur',
        fixedValue: 100.0,
        savedAmount: 150.0,
      },
      {
        description: 'Velo Reparatur',
        fixedValue: 20.0,
        savedAmount: 40.0,
      },
      {
        description: 'Coiffeur',
        fixedValue: 15,
        savedAmount: 5,
      },
      {
        description: 'Konzerte',
        fixedValue: 40.0,
        savedAmount: 200.0,
      },
    ]"
    @clickedMonthlySavingCard="(index) => test(index)"
  />
</template>

<script>
import MonthlySavingOverview from "@/components/MonthlySavingOverview.vue";
export default {
  name: "DevPreview",
  components: {
    MonthlySavingOverview,
  },
  methods: {
    test(index) {
      console.log("click ", index);
    },
  },
};
</script>
