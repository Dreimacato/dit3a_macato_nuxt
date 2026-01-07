<template>
 <div>
    <v-app>
        <v-navigation-drawer
        v-model="drawer"
      >
        <v-list>
          <v-list-item
            prepend-avatar="https://wallpapers.com/images/hd/emo-pfp-glitch-art-7qqilpb5ekmuswub.jpg"
            subtitle="DIT-3A"
            title="Andrei Anakin Macato"
          ></v-list-item>
        </v-list>

        <v-divider></v-divider>

        <v-list density="compact" nav>
          <v-list-item to="/" prepend-icon="mdi mdi-view-dashboard" title="Dashboard" value="myfiles"></v-list-item>
          <v-list-item to="inventory" prepend-icon="mdi-account-multiple" title="Inventory" value="shared"></v-list-item>
          <v-list-item to="Category" prepend-icon="mdi mdi-shape-plus" title="Category" value="starred"></v-list-item>
          <v-list-item to="user" prepend-icon="mdi mdi-shape-plus" title="User" value="starred"></v-list-item>
        </v-list>
      </v-navigation-drawer>

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
 </div>
</template>

<script setup>
const drawer = ref(true)
</script>
