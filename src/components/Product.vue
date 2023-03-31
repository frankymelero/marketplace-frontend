<template>
    <div>
      <h2>Productos:</h2>
      <ul>
        <li v-for="product in products" :key="product.id">
          {{ product.name }} - {{ product.description }}
        </li>
      </ul>
    </div>
  </template>
  
  <script setup>
    const props = ['products'];
  </script>