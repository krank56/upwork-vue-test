<script setup lang="ts">
import { ref } from "vue";
import Card from "./components/Card.vue";

interface CardItems {
  title: string;
  list?: string[];
  description: string;
  images?: string[];
}

interface Cards extends Array<CardItems> {}

const cards: Cards = [
  {
    title: "Photography",
    list: ["Drone Photography", "Interiors", "Exteriors / Architectural"],
    description:
      "Every photograph we produce finds the beauty in your property while serving as a profitable asset.",
    images: [
      "./assets/images/photography-1.png",
      "./assets/images/photography-2.png",
    ],
  },
  {
    title: "Videography",
  },
  {
    title: "Virtual Tours",
  },
  {
    title: "3D Tours",
  },
  {
    title: "Floor Plans",
  },
  {
    title: "Aerial Photography",
  },
];
</script>

<template>
  <div class="container">
    <h1 class="title">
      We make creative media that <span class="emph">adds value</span>
    </h1>

    <div class="grid-container">
      <Card
        v-for="card in cards"
        :key="card.id"
        :title="card.title"
        :description="card.description"
        :image="card.image"
      />
    </div>
  </div>
</template>

<style lang="scss">
@import "./scss/variables.scss";

// reset css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: $font-family;
  color: $color_charcoal;
  background: $color_background;
}

// global css
h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: $font-family;
  font-weight: 700;
  color: $color_dark_blue;
}

.title {
  max-width: 730px;
  margin: auto;
  text-align: center;
  font-size: 3.5rem;
  line-height: 1;
  margin-bottom: 1rem;
}

p {
  font-family: $font-family;
  font-weight: 600;
  color: $color_charcoal;
}

ul li::before {
  color: $color_tan;
  content: "\2022";
  display: inline-block;
  width: 1em;
  margin-left: -1em;
}

.emph {
  color: $color_blue;
}

.container {
  max-width: 1200px;
  margin: 6rem auto;
  padding: 0 1rem;
}

.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  grid-gap: 1rem;
}
</style>
