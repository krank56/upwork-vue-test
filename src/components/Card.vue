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
      <ul class="card__list" v-if="props.list">
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
  overflow: hidden;
  &__image {
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 2px;
    flex: 0 0 183px;
    @media (max-width: 768px) {
      flex: 0 0 30%;
    }
    img {
      flex: auto;
      width: 100%;
      height: 100%;
      object-fit: cover;
      object-position: center;
    }
  }
  &__content {
    width: 100%;
    height: 100%;
    padding: 40px 30px;
    @media (max-width: 768px) {
      padding: 25px 20px;
    }
    flex: auto;
  }
  &__title {
    font-size: 24px;
    line-height: 32px;
    margin-bottom: 12px;
    color: $color_charcoal;
  }
  &__list {
    margin-bottom: 12px;
  }
}
</style>
