<script setup lang="ts">
</script>
<template>
  <v-container fluid>
  <!-- Navbar -->
  <v-app-bar flat color="grey-lighten-4">
    <v-container class="d-flex align-center">
      <!-- Logo -->
      <v-toolbar-title class="font-weight-bold">Atlantis</v-toolbar-title>

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

  <!-- Hero Section -->
<v-container class="hero-section">
  <v-row align="center">
    <!-- Columna Izquierda - Texto -->
    <v-col cols="12" md="6" class="text-left pa-8">
      <h1 class="text-h3 font-weight-bold text-white">Diversify your portfolio</h1>
      <p class="text-subtitle-1 text-white">
        Invest in real estate with confidence and diversify your portfolio.
      </p>
      <v-btn color="white" class="mt-4" size="large" variant="outlined">
        Register now →
      </v-btn>
    </v-col>

    <!-- Columna Derecha - Imagen -->
    <v-col cols="12" md="6" class="text-center">
      <v-img
        src="https://media.istockphoto.com/id/1990444472/photo/scandinavian-style-cozy-living-room-interior.jpg?s=1024x1024&w=is&k=20&c=kHJB-lnK-XmClW7tcWCO68POsyd6H3v0RA5IWCEODb4="
        alt="Real estate image"
        class="hero-image"
        contain
      />
    </v-col>
  </v-row>
</v-container>

</v-container>
</template>

<style scoped>
.hero-section {
  background: linear-gradient(135deg, #5B46F2, #9069F2);
  padding: 100px 0;
  border-radius: 0 0 50px 50px;
}
</style>