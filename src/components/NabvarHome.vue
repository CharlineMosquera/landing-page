<script setup>
const icons = ['mdi-facebook', 'mdi-twitter', 'mdi-linkedin', 'mdi-instagram'];
</script>

<template>
  <v-app-bar flat color="grey-lighten-4">
    <v-container class="d-flex align-center">
      <!-- Logo -->
       <v-btn text to="/">
        <v-toolbar-title class="font-weight-bold">Atlantis</v-toolbar-title>
       </v-btn>

      <!-- Espaciador -->
      <v-spacer></v-spacer>

      <!-- Links  -->
      <v-btn text to="/about">About Us</v-btn>
      <v-btn text to="/education">Education</v-btn>
      <v-btn text to="/opportunities">Opportunities</v-btn>
      <v-btn text to="/blog">Blog</v-btn>

      <!-- Espaciador -->
      <v-spacer></v-spacer>

      <!-- Botones a la derecha -->
      <v-btn variant="outlined" color="primary" to="/login">Login</v-btn>
      <v-btn color="black" class="ml-2" to="/signup">Sign Up</v-btn>
    </v-container>
  </v-app-bar>
</template>
