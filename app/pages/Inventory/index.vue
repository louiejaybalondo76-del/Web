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

<!-- Selectable inventory -->
    <v-select
    v-model="selectedCategory"
  clearable
  label="Select Category"
  :items="category.data"
  item-title="category_name"
  item-value="id"
  variant="outlined"
></v-select>

    <v-data-table
      :headers="headers"
      :items="filteredInventory"
      :search="search"
    ></v-data-table>
  </v-card>
</template>

<script setup>
  import { ref } from 'vue'
  const search = ref('');
  
  const selectedCategory = ref (null);

  const { data: inventory} = await useFetch('http://localhost:1337/api/inventories?populate=category');
  

  const { data: category } = await useFetch('http://localhost:1337/api/categories');

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
    { key: 'total_cost', title: 'Total Cost' },
    { key: 'remarks', title: 'Remarks' },
    
    
  ];
  const filteredInventory = computed(()=>{
    if(!selectedCategory.value){
      return inventory.value.data;
    }else{
      return inventory.value.data.filter(item =>item.category.id === selectedCategory.value);
    }
  });
</script>