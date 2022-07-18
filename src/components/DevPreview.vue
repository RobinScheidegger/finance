<template>
  <MonthlySavingCard @clickedCard="test()" />
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
