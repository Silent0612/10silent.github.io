<template>
  <div class="recipe-list">
    <el-card v-for="recipe in recipes" :key="recipe.id" :header="recipe.title" @click="selectRecipe(recipe)">
      <el-image :src="recipe.image"></el-image>
    </el-card>
  </div>
</template>

<script>
export default {
  props: ['recipes'],
  methods: {
    selectRecipe(recipe) {
      this.$emit('select-recipe', recipe)
    }
  }
}
</script>

<style scoped>
.recipe-list {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>