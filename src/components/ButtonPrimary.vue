<script setup lang="ts">
import { defineProps } from "vue";

export interface ButtonPrimaryProps {
  label: string;
  href: string;
}

const props = defineProps<ButtonPrimaryProps>();
</script>
<template>
  <a :href="props.href"
    ><span>{{ label }}</span></a
  >
</template>

<style scoped lang="scss">
@import "./../scss/variables.scss";
a {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 315px;
  height: 60px;
  background: $color_dark_blue;
  border-radius: 12px;
  span {
    color: $color_white;
  }
  margin: auto;
}
</style>
