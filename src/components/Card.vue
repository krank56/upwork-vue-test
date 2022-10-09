<script setup lang="ts">
import { defineProps } from "vue";

export interface CardProps {
  id: number;
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
      <img v-for="image in props.images" :src="image" />
    </div>
    <div class="card__content">
      <h3 class="card__title">{{ props.title }}</h3>
      <ul v-if="props.list">
        <li v-for="item in props.list" :key="item">{{ item }}</li>
      </ul>
      <p class="card__description">{{ props.description }}</p>
    </div>
  </div>
</template>
<style scoped lang="scss">
@import "./../scss/variables.scss";
.card {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  height: 100%;
  background: $color_white;
  border-radius: 8px;
  box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.25);
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
