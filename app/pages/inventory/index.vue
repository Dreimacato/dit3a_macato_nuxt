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

    <v-select
    v-model="selectedCategory"
  clearable
  label="Select Category"
  :items="category.data"
  variant ="outlined"
  item-title="category_name"
  item-value="id"
  class="mx-4"
></v-select>

    <v-data-table
      :headers="headers"
      :items="inventory.data"
      :search="search"
    ></v-data-table>
  </v-card>
</template>
 <script setup>
    const { data: inventory } = await useFetch('http://localhost:1337/api/inventories?populate=category');

    const { data: category} = await useFetch('http://localhost:1337/api/categories');

    

    const selectedCategory = ref(null);

  const search = ref('')
  const headers = [
 

    { key: 'product_name', title: 'product_name' },
    { key: 'product_description', title: 'Description' },
    { key: 'quantity', title: 'quantity' },
    { key: 'unit', title: 'unit' },
    { key: 'condition', title:'condition' },
     { key: 'location', title:'location' },
    { key: '', title:'Actions'},
  ]

  const filterCategory = computed(() =>{
    if(!selectedCategory.value){
      return inventory.value.data;
    }else{
      return inventory.value.data.filter(item =>
        item.category.id === selectedCategory.value
      )
    }

  })
0</script>