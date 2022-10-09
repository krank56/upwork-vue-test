<script setup lang="ts">
import { defineProps } from "vue";

interface CardProps {
  title: string;
  description: string;
  list?: string[];
  images?: string[];
}

const props = defineProps<CardProps>();
</script>
<template>
  <div class="card">
    <div class="card__image">
      <img :src="props.image" alt="" />
    </div>
    <div class="card__content">
      <h3 class="card__title">{{ props.title }}</h3>
      <p class="card__description">{{ props.description }}</p>
    </div>
  </div>
</template>
<style scoped lang="scss">
@import "./../scss/variables.scss";
.card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  height: 100%;
  background: $color_white;
  border-radius: 10px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.25);
  padding: 1rem;
  margin: 1rem;
  transition: all 0.3s ease-in-out;
  &:hover {
    transform: translateY(-5px);
  }
  &__image {
    width: 100%;
    height: 100%;
    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      border-radius: 10px;
    }
  }
  &__content {
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
    &__title {
      font-size: 1.5rem;
      text-align: center;
      margin-bottom: 1rem;
    }
    &__description {
      font-size: 1rem;
      text-align: center;
    }
  }
}
</style>
