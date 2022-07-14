<template>
  <div class="icon-card">
    <img class="icon-card__icon" src="@/assets/icons/icon-settings.jpg" />
  </div>
</template>

<script>
export default {
  name: "IconCard",
  props: {
    icon: {
      type: String,
      default: "icon-settings",
    },
    size: {
      type: Number,
      default: 24,
    },
  },
};
</script>
