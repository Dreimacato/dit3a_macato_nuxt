<template>
  category
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

      <v-select
  clearable
  label="Select"
  :items="category.data"
  variant="outlined"
  item-title="category_name"
  item-value="id"
  class="mx-4"
></v-select>

    <v-data-table
      :headers="headers"
      :items="category.data"
      :search="search"
    ></v-data-table>
  </v-card>

      <v-data-table
      :headers="headers"
      :items="inventory.data"
      :search="search"
    ></v-data-table>

  <v-select
  clearable
  label="Select"
  :items="category.data"
  variant="outlined"
  item-title="category_name"
  class="mx-4"
></v-select>

</template>
<script setup>
  // import { ref } from 'vue'
  const { data: category } = await useFetch('http://localhost:1337/api/categories');

  const search = ref('')
  const headers = [
    { key: 'category_name', title: 'Category Name' },
    { key: 'description', title: 'Description' },
    { key: 'category_name2', title: 'Category Name2' },
    { key: 'description', title: 'Description2' },
   
  ]
  
</script>