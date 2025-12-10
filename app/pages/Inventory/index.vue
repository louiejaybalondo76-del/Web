<template>
  <v-card
    title="Inventory"
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
  const { data: category } = await useFetch('http://localhost:1337/api/inventories');
  const headers = [
    { key: 'product_name', title: 'Product Name' },
    { key: 'product_description', title: 'Prodcut Description' },
    { key: 'quantity', title: 'Quantity' },
    { key: 'unit', title: 'Unit' },
    { key: 'condition', title: 'Condtion' },
    { key: 'location', title: 'Location' },
    { key: 'total_cost', title: 'Total Cost' },
    { key: 'acquisition_date', title: 'Acquisition Date' },
    { key: 'acquisition_cost', title: 'Acquisition Cost' },
    { key: 'remarks', title: 'Remarks' },
    
    
  ];
</script>