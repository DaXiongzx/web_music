<template>
  <div class="the-footer">
    <p v-for="(item, index) in footerList" :key="index">
      {{ item }}
    </p>
  </div>
</template>

<script lang="ts">
import { defineComponent, readonly } from "vue";

export default defineComponent({
  setup() {
    const footerList = readonly([
      
    ]);

    return { footerList };
  },
});
</script>

<style lang="scss" scoped>
@import "@/assets/css/var.scss";
@import "@/assets/css/global.scss";

.the-footer {
  width: 100%;
  padding: 20px 0;
  background-color: $theme-footer-color;
  @include layout(center, center, column);
}

p {
  height: 30px;
}
</style>
