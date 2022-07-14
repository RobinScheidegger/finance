<template>
  <div class="card-border">
    <slot />
  </div>
</template>

<script>
export default {
  name: "CardBorder",
};
</script>

<style>
.card-border {
  background-color: #ffffff;
  border: 1px solid #e1e1e1;
  border-radius: 12px;
}
</style>
