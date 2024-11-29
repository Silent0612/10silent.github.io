<template>
  <div id="app">
    <header>
      <h1>创意食谱分享网站</h1>
    </header>
    <main>
      <recipe-list :recipes="recipes" @select-recipe="handleSelectRecipe"></recipe-list>
      <recipe-detail :recipe="selectedRecipe" v-if="selectedRecipe"></recipe-detail>
    </main>
  </div>
</template>

<script>
import RecipeList from './components/RecipeList.vue'
import RecipeDetail from './components/RecipeDetail.vue'
import recipesData from './data/recipes.json'

export default {
  name: 'App',
  components: {
    RecipeList,
    RecipeDetail
  },
  data() {
    return {
      recipes: recipesData,
      selectedRecipe: null
    }
  },
  methods: {
    handleSelectRecipe(recipe) {
      this.selectedRecipe = recipe
    }
  }
}
</script>

<style>
#app {
  text-align: center;
}
</style>