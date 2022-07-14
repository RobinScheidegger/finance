<template>
  <div class="icon-card">
    <img
      class="icon-card__icon"
      :src="require(`@/assets/icons/icon-${icon}.jpg`)"
      :style="style"
    />
  </div>
</template>

<script>
export default {
  name: "IconCard",
  props: {
    icon: {
      type: String,
      default: "settings",
    },
    size: {
      type: Number,
      default: 32,
    },
  },

  computed: {
    style() {
      return "width: " + this.size + "px";
    },
  },
};
</script>
