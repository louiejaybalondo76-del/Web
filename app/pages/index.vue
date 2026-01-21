<template>
  <v-container fluid class="d-flex justify-center align-center"style="height:100vh ;">
    
    
    <v-card
      class="mx-auto pa-12 pb-8 "
      elevation="8"
      max-width="448"
      rounded="lg"
      
    >
    <v-img
      class="mx-auto my-6"
      max-width="500"
      src="https://static.vecteezy.com/system/resources/previews/005/050/797/original/library-logo-template-design-free-vector.jpg"
    ></v-img>
      <div class="text-subtitle-1 text-medium-emphasis">Account</div>

      <v-text-field
        density="compact"
        placeholder="Email address"
        prepend-inner-icon="mdi-email-outline"
        variant="outlined"
      ></v-text-field>

      <div class="text-subtitle-1 text-medium-emphasis d-flex align-center justify-space-between">
        Password

        <a
          class="text-caption text-decoration-none text-grey-darken-4"
          href="#"
          rel="noopener noreferrer"
          target="_blank"
        >
          Forgot login password?</a>
      </div>

      <v-text-field
        :append-inner-icon="visible ? 'mdi-eye-off' : 'mdi-eye'"
        :type="visible ? 'text' : 'password'"
        density="compact"
        placeholder="Enter your password"
        prepend-inner-icon="mdi-lock-outline"
        variant="outlined"
        @click:append-inner="visible = !visible"
      ></v-text-field>

      <v-card
        class="mb-12"
        color="surface-variant"
        variant="tonal"
      >
        <v-card-text class="text-grey-darken-4 text-caption">
          Warning: After 3 consecutive failed login attempts, you account will be temporarily locked for three hours. If you must login now, you can also click "Forgot login password?" below to reset the login password.
        </v-card-text>
      </v-card>

      <v-btn 
        to="/dashboard"
        class="mb-8"
        color="grey-darken-4"
        size="large"
        variant="tonal"
        block
      >
        Log In
      </v-btn>

      <v-card-text class="text-center">
        <a
          class="text-grey-darken-4 text-decoration-none"
          href="#"
          rel="noopener noreferrer"
          target="_blank"
        >
          Sign up now <v-icon icon="mdi-chevron-right"></v-icon>
        </a>
      </v-card-text>
    </v-card>
  </v-container>
</template>

    <script lang="ts" setup>
        definePageMeta({
            layout:false,
        });
        const visible = ref(false)
    </script>

    <style>
    
    </style>