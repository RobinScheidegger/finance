<template>
  <div class="icon-card" :style="height">
    <img
      class="icon-card__icon"
      :src="require(`@/assets/icons/icon-${type}.jpg`)"
      :style="style"
    />
  </div>
</template>

<script>
export default {
  name: "IconCard",
  props: {
    type: {
      type: String,
      default: "settings",
    },
    size: {
      type: Number,
      default: 24,
    },
    opacity: {
      type: Number,
      default: 1,
    },
  },

  computed: {
    style() {
      return "width: " + this.size + "px;" + "opacity: " + this.opacity + ";";
    },
    height() {
      return "height: " + this.size + "px;";
    },
  },
};
</script>
