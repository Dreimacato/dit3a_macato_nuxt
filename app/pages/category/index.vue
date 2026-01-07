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
 const { data: category} = await useFetch('http://localhost:1337/api/categories');

 const { data: inventory } = await useFetch('http://localhost:1337/api/inventories');

 
 

  const search = ref('')
  const headers = [
 
    { key: 'category_id', title: 'Category_id' },
    { key: 'category_name', title: 'Category_name' },
    { key: 'description', title: 'Description' },
    { key: 'date_created', title: 'date_created' },
  ]
 
  
</script>