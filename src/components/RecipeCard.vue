<template>
  <div class="card">
    <div class="card-tab">
      <a :href="card.link" class="text name" target="_blank">{{ card.name }}</a>
    </div>
    <div class="card-internal">
      <span class="text">Total Calories:</span>
      <span class="text total-calories">{{ totalCalories }}</span>
      <span class="text">Gluten Free:</span>
      <span class="text gluten-free">{{ glutenFree }}</span>
      <img class="image" :src="card.imageLink" />
    </div>
  </div>
</template>

<style lang="scss">
.card {
  color: #333;
  &-tab {
    text-align: left;
    overflow: hidden;
    width: 90%;
    .name {
      display: inline-block;
      width: auto;
      border-radius: 5px 5px 0 0;
      background-color: white;
      padding: 5px 5px 0px;
      text-overflow: ellipsis;
    }
  }
  &-internal {
    padding: 10px 5px 5px;
    display: grid;
    grid-template-columns: auto auto;
    grid-template-rows: 10% auto;
    grid-column-gap: 20px;
    grid-row-gap: 20px;
    justify-items: start;
    align-items: stretch;
    background: white;
    border-radius: 0 5px 5px 5px;
    .text {
      text-align: left;
    }
    .image {
      max-width: 100%;
      grid-column: 1/3;
    }
  }
}
</style>

<script lang="ts">
import Vue from "vue";
import { Component, Prop } from "vue-property-decorator";

@Component
export default class RecipeCard extends Vue {
  @Prop({ default: null })
  card: any;

  get totalCalories() {
    return this.card.totalCalories
      ? this.card.totalCalories
      : this.card.numberOfServings * this.card.caloriesPerServing;
  }

  get isGlutenFree() {
    return this.card.glutenFree ? "Gluten Free" : "GF Options";
  }

  get glutenFree() {
    return this.card.glutenFreeOptions ? this.card.glutenFreeOptions : "N/A";
  }
}
</script>

<style></style>
