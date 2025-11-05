<template>
  <v-container fluid>
    
    <v-app>

   
      <v-navigation-drawer
      v-model="drawer"
      >
        <v-list>
          <v-list-item
            prepend-avatar="https://randomuser.me/api/portraits/men/85.jpg"
            subtitle="andreimacato09@gmail.com"
            title="Andrei Anakin T. Macato"
          ></v-list-item>
        </v-list>

        <v-divider></v-divider>

        <v-list density="compact" nav>
           <v-list-item to="user" prepend-icon="mdi-account" title="User" value="starred"></v-list-item>
          <v-list-item to="/" prepend-icon="mdi mdi-view-dashboard" title="Dashboard" value="myfiles"></v-list-item>
          <v-list-item to="inventory" prepend-icon="mdi mdi-database" title="Inventory" value="shared"></v-list-item>
          <v-list-item to="category" prepend-icon="mdi-star" title="Category" value="starred"></v-list-item>
        </v-list>
      </v-navigation-drawer>

      <v-main style="height: 250px"></v-main>



    <v-app-bar :elevation="2">
  <template v-slot:prepend>
    <v-app-bar-nav-icon @click.stop="drawer =! drawer"></v-app-bar-nav-icon>
  </template>

  <v-app-bar-title>Application Bar</v-app-bar-title>
</v-app-bar>

    <v-main>
      <v-container fluid>
          <slot/>
      </v-container>
      
    </v-main>
    </v-app>
    
  </v-container>
</template>

<script setup>
  const drawer = ref(true)
</script>

