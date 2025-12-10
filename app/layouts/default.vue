<template>
    <div>
        <v-app>
        <!--Navigation -->
        <v-navigation-drawer
        v-model="drawer"



      >
        <v-list>
          <v-list-item
prepend-avatar="https://i.pinimg.com/originals/16/78/06/16780663b8511b3e2ff84d62427313b5.jpg"
          subtitle="Louiejaybalondo@gmail.com"
            title="Louie Jay R. Balondo"
          ></v-list-item>
        </v-list>

        <v-divider></v-divider>

        <v-list density="compact" nav>
          <v-list-item to="/" prepend-icon="mdi mdi-view-dashboard" title="Dashboar" value="dashboard"></v-list-item>
          <v-list-item to="/Inventory" prepend-icon="mdi mdi-list-box" title="Inventory" value="inventory"></v-list-item>
          <v-list-item to="/Category"prepend-icon="mdi mdi-account-group-outline" title="Category" value="category"></v-list-item>
          <v-list-item to="/Users"prepend-icon="mdi mdi-account-group-outline" title="Users" value="user"></v-list-item>
        </v-list>
      </v-navigation-drawer>


        <!--Appbar -->
        <v-app-bar :elevation="2">
  <template v-slot:prepend>
    <v-app-bar-nav-icon @click.stop="drawer =! drawer"></v-app-bar-nav-icon>
  </template>

  <v-app-bar-title>Application Bar</v-app-bar-title>
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