<script setup lang="ts">
import Card from "./components/Card.vue";
import ButtonPrimary from "./components/ButtonPrimary.vue";
import type { CardProps } from "./components/Card.vue";
import type { ButtonPrimaryProps } from "./components/ButtonPrimary.vue";

interface Cards extends Array<CardProps> {}

const cards: Cards = [
  {
    id: 1,
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
    id: 2,
    title: "Virtual Staging",
    description:
      "Our staging will help you sell the potential of your space. We can work off of our own photography or photos you provide.",
    images: ["./assets/images/virtual-staging-1.png"],
  },
  {
    id: 3,
    title: "Renderings",
    list: ["Interiors", "Exteriors"],
    description:
      "Renderings are the gold standard in pre-construction marketing.",
    images: ["./assets/images/renderings-1.png"],
  },
  {
    id: 4,
    title: "Interactive Tours",
    list: ["Video Walkthroughs", "Floor Plans"],
    description:
      "Give your audience the ability to explore your property without requiring in-person travel.",
    images: ["./assets/images/interactive-tours-1.png"],
  },
  {
    id: 5,
    title: "Floor Plans",
    list: ["On-site Measure", "2D Floor Plans", "3D Floor Plans"],
    description:
      "We produce laser-precise floor plans faster than any other service.",
    images: ["./assets/images/floor-plans-1.png"],
  },
  {
    id: 6,
    title: "Video",
    list: ["Drone Cinematography", "Interiors", "Exteriors / Architectural"],
    description:
      "Video content has higher engagement and will help your property stand out online.",
    images: ["./assets/images/video-1.png"],
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
        :id="card.id"
        :title="card.title"
        :list="card.list"
        :description="card.description"
        :images="card.images"
      />
    </div>

    <ButtonPrimary :href="'#'" :label="'Get started'" />
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

//reset link styling
a {
  text-decoration: none;
}

body {
  font-family: $font-family-poppins;
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
  font-family: $font-family-poppins;
  font-weight: 700;
  color: $color_dark_blue;
}

.title {
  max-width: 730px;
  margin: auto;
  text-align: center;
  font-size: 56px;
  line-height: 1;
  margin-bottom: 80px;
}

p {
  font-family: $font-family-nunito;
  font-weight: 600;
  color: $color_charcoal;
  font-size: 15px;
  line-height: 24px;
}

ul {
  list-style: none;
  li::before {
    color: $color_tan;
    content: "\2022";
    display: inline-block;
    width: 1em;
  }
  li {
    font-family: $font-family-nunito;
    font-size: 15px;
    line-height: 26px;
    font-weight: 700;
  }
}

.emph {
  color: $color_blue;
}

.container {
  max-width: 1440px;
  margin: 6rem auto;
  padding: 0 2rem;
}

.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(437.5px, 1fr));
  grid-column-gap: 30px;
  grid-row-gap: 40px;
  @media (max-width: 768px) {
    grid-template-columns: repeat(auto-fill, minmax(100%, 1fr));
  }
  margin-bottom: 80px;
}
</style>
