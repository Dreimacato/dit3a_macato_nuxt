<template>
  <div>
    <v-app>

      <v-navigation-drawer
        v-model="drawer"
      >
        <v-list>
          <v-list-item
            prepend-avatar="https://randomuser.me/api/portraits/men/85.jpg"
            subtitle="andreimacato09@gmail.com"
            title="Andrei Anakin Macato"
          ></v-list-item>
        </v-list>

        <v-divider></v-divider>

        <v-list density="compact" nav>
          <v-list-item to="/" prepend-icon="mdi-folder" title="Dashboard" value="myfiles"></v-list-item>
          <v-list-item to="Inventory" prepend-icon="mdi-account-multiple" title="Inventory" value="shared"></v-list-item>
          <v-list-item to="Category" prepend-icon="mdi-layers-triple" title="Category" value="starred"></v-list-item>
          <v-list-item to="User" prepend-icon="mdi-account" title="User" value="starred"></v-list-item>
        </v-list>
      </v-navigation-drawer>

      <v-app-bar :elevation="2">
  <template v-slot:prepend>
    <v-app-bar-nav-icon @click.stop="drawer =! drawer"></v-app-bar-nav-icon>

  </template>

  <v-app-bar-title>Andrei Anakin Macato - DIT3A</v-app-bar-title>
</v-app-bar>

  <v-main>
    <v-container fluid>
      <slot/>
    </v-container>
  </v-main>
  </v-app>

  </div>
</template>

<script setup>
  const drawer = ref(true)
</script>