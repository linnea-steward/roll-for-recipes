<template>
  <div class="home">
    <div class="filter"></div>
    <div class="grid">
      <recipe-card
        v-for="(card, index) in cards"
        v-bind:key="card.timestamp"
        v-bind:index="index"
        v-bind:card="card"
      ></recipe-card>
    </div>
  </div>
</template>

<style lang="scss">
.home {
  .grid {
    display: grid;
    grid-template-rows: auto;
    grid-column-gap: 1rem;
    grid-row-gap: 1rem;

    @for $i from 1 through 12 {
      @media (min-width: #{320 * $i}px) {
        grid-template-columns: repeat($i, 1fr);
      }
    }
  }
}
</style>

<script>
// @ is an alias to /src
import Vue from "vue";
import { Component, Prop } from "vue-property-decorator";
import RecipeCard from "@/components/RecipeCard.vue";
import axios from "axios";

@Component
export default class Home extends Vue {
  cards: any[];
}

export default {
  name: "home",
  data: () => {
    return {
      cards
    };
  },
  components: {
    RecipeCard
  },
  created: () => {
    axios
      .get("https://api.sheety.co/140bb7d0-0b81-4c8a-9fcb-123a9e7cf840")
      .then(response => {
        this.cards = response;
      });
  }
};
</script>
