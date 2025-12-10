<template>
  <v-card
    title="Category"
    flat
  >
    <template v-slot:text>
      <v-text-field
        v-model="search"
        label="Search"
        prepend-inner-icon="mdi-magnify"
        variant="outlined"
        hide-details
        single-line
      ></v-text-field>
    </template>

    <v-data-table
      :headers="headers"
      :items="category.data"
      :search="search"
    ></v-data-table>
  </v-card>
</template>

<script setup>
  import { ref } from 'vue'
  const search = ref('')
  const { data: category } = await useFetch('http://localhost:1337/api/categories?populate=inventories');
  const headers = [
    { key: 'category_name', title: 'Category Name' },
    { key: 'description', title: 'Description' },
    { key: 'createdAt', title: 'Creat Date' },
    { key: 'publishedAt', title: 'Publish Date' },
    { key: '', title: '' },
  ];
</script>