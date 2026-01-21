<template>
    <div>
        <v-app>
        <!--Navigation -->
        <v-navigation-drawer
        v-model="drawer"



      >
        <v-list>
          <v-list-item
prepend-avatar=""
          subtitle="Admin@gmail.com"
            title="ADMIN"
          ></v-list-item>
        </v-list>

        <v-divider></v-divider>

        <v-list density="compact" nav>
          <v-list-item to="/Dashboard" prepend-icon="mdi mdi-view-dashboard" title="Dashboard" value="dashboard"></v-list-item>
          <v-list-item to="/Inventory" prepend-icon="mdi mdi-list-box" title="Inventory" value="inventory"></v-list-item>
          <v-list-item to="/Category"prepend-icon="mdi mdi-account-group-outline" title="Category" value="category"></v-list-item>
          <v-list-item to="/Users"prepend-icon="mdi mdi-account-tie" title="Users" value="user"></v-list-item>
          <v-list-item to="/"prepend-icon="mdi mdi-logout" title="Sign Out" value="signout"></v-list-item>
        </v-list>
      </v-navigation-drawer>


        <!--Appbar -->
        <v-app-bar :elevation="2">
  <template v-slot:prepend>
    <v-app-bar-nav-icon @click.stop="drawer =! drawer"></v-app-bar-nav-icon>
  </template>

  <v-app-bar-title><h1>ONLINE LIBRARY MANAGEMENT SYSTEM</h1></v-app-bar-title>
</v-app-bar>



            <v-main>
                <v-container fluid>
                <slot />
                </v-container>
            </v-main>
        </v-app>
    </div>

</template>

    <script  setup>
    const drawer = ref(true)

    </script>