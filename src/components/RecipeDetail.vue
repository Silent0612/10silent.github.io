<template>
    <div class="recipe-detail">
      <h2>{{ recipe.name }}</h2>
      <h3>配料</h3>
      <el-list>
        <el-list-item v-for="ingredient in recipe.ingredients" :key="ingredient">{{ ingredient }}</el-list-item>
      </el-list>
      <h3>烹饪步骤</h3>
      <el-steps :space="200">
        <el-step v-for="(step, index) in recipe.steps" :key="index" :title="step"></el-step>
      </el-steps>
    </div>
  </template>
  
  <script>
  export default {
    props: ['recipe']
  }
  </script>
  
  <style scoped>
  .recipe-detail {
    text-align: left;
    margin: 20px;
  }
  </style>