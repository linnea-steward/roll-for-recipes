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

<script>
// @ is an alias to /src
import RecipeCard from "@/components/RecipeCard.vue";

let cards = [];
cards = [
  {
    timestamp: "3/6/2019 17:40:07",
    name: "Instant Pot Pasta with Spinach and Sausage",
    link:
      "https://www.rachelcooks.com/2018/03/12/instant-pot-pasta-sausage-spinach/print/",
    totalCalories: null,
    numberOfServings: 6,
    caloriesPerServing: 300,
    method: "Instant Pot",
    ethnicity: "Italian",
    meal: "lunch, dinner",
    imageLink:
      "https://www.rachelcooks.com/wp-content/uploads/2018/03/instant-pot-pasta-sausage-web-4-of-4-600x789.jpg",
    glutenFree: false,
    glutenFreeOptions: "Replace pasta with GF pasta",
    protein: "Turkey Sausage",
    grains: "Pasta",
    veggies: "Tomatoes, Spinach",
    spices: "Oregano",
    otherSupplies: "Olive Oil",
    totalCookTime: null
  },
  {
    timestamp: "3/6/2019 21:41:15",
    name: "Keto Beef Egg Roll Slaw",
    link: "https://www.allrecipes.com/recipe/264086/keto-beef-egg-roll-slaw/",
    totalCalories: null,
    numberOfServings: 6,
    caloriesPerServing: 350,
    method: "Saute",
    ethnicity: "Asian-American",
    meal: "Lunch, Dinner",
    imageLink:
      "https://images.media-allrecipes.com/userphotos/560x315/5327131.jpg",
    glutenFree: "Yes",
    glutenFreeOptions: null,
    protein: "Ground Beef",
    grains: null,
    veggies: "Green Onion, Yellow Onion, Coleslaw",
    spices: "Ground Ginger",
    otherSupplies: "Sesame Oil, Soy Sauce, Apple Cider Vinegar, Sriracha",
    totalCookTime: null
  },
  {
    timestamp: "3/6/2019 21:45:37",
    name: "BLT Chicken Salad",
    link:
      "https://www.allrecipes.com/recipe/16466/chicken-salad-with-bacon-lettuce-and-tomato/",
    totalCalories: null,
    numberOfServings: 6,
    caloriesPerServing: 456,
    method: "Skillet",
    ethnicity: "American",
    meal: "Lunch, Dinner",
    imageLink:
      "https://images.media-allrecipes.com/userphotos/720x405/786271.jpg",
    glutenFree: "Yes",
    glutenFreeOptions: null,
    protein: "Bacon, Chicken",
    grains: null,
    veggies: "Green Onion, Tomato, Avocado",
    spices: null,
    otherSupplies: "Mayo, Worcestershire Sauce, Lemon Juice",
    totalCookTime: null
  }
];

export default {
  name: "home",
  data: () => {
    return {
      cards
    };
  },
  components: {
    RecipeCard
  }
};
</script>
