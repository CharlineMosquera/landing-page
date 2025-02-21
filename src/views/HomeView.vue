<script setup lang="ts">
import img1 from '@/assets/img/card1Blog.png';
import img2 from '@/assets/img/bodyHome.png';


const icons = ['mdi-facebook', 'mdi-twitter', 'mdi-linkedin', 'mdi-instagram'];
const links = ['About Us','Education','Opportunities','Blog',]
</script>
<template>
  <v-container fluid>
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
    <v-col cols="12" md="6" class="text-center pa-6">
      <v-img
        :src="img1"
        alt="Real estate image"
        class="hero-image rounded-xl"
        contain
      />
    </v-col>
  </v-row>
</v-container>
<!-- Sección "What do we offer?" -->
<v-container class="offer-section mt-10">
      <v-row justify="center">
        <v-col cols="12" class="text-center">
          <h2 class="text-h4 font-weight-bold">What do we offer you?</h2>
          <p class="text-subtitle-1">Invest in Real Estate (Lease ed Properties and Debt) to protect your capital and build your future</p>
        </v-col>
      </v-row>
      <v-row align="center">
        <v-col cols="12" md="6">
          <v-img :src="img2" alt="Investment image" class="rounded-lg" />
        </v-col>
        <v-col cols="12" md="6">
          <v-list >
            <v-list-item class="pa-6" v-for="(item, index) in [
              { title: 'Flexible investment structures', text: 'Our platform offers personalized support and a secure bridge to protect your capital.' },
              { title: 'Access and variety of projects', text: 'Our goal is to help you diversify and mitigate risks in your investment portfolio.' },
              { title: 'Technology and transparency', text: 'Our platform leverages technology to provide a seamless and transparent investment experience.' },
              { title: 'Predictable income streams', text: 'Projects with due diligence ensure a stable and predictable income flow.' }
            ]" :key="index">
              <template v-slot:prepend>
                <span class="text-primary font-weight-bold text-h6">{{ `0${index + 1}` }}</span>
              </template>
              <v-list-item-title class="font-weight-bold pa-2">{{ item.title }}</v-list-item-title>
              <v-list-item-subtitle class="pa-4">{{ item.text }}</v-list-item-subtitle>
            </v-list-item>
          </v-list>
        </v-col>
      </v-row>
    </v-container>

    <!-- Sección de estadísticas -->
    <v-container class="stats-section py-10 text-center">
      <v-row>
        <v-col cols="12" md="4">
          <h2 class="text-h4 font-weight-bold text-primary">+60</h2>
          <p>Properties</p>
        </v-col>
        <v-col cols="12" md="4">
          <h2 class="text-h4 font-weight-bold text-primary">+35M</h2>
          <p>Volume</p>
        </v-col>
        <v-col cols="12" md="4">
          <h2 class="text-h4 font-weight-bold text-primary">+5</h2>
          <p>Cities</p>
        </v-col>
      </v-row>
    </v-container>
     <!-- Benefits Section -->
    <v-container class="benefits-section py-10">
      <v-row>
        <v-col cols="12" class="text-center">
          <h2 class="text-h4 font-weight-bold">Benefits of investing with us</h2>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="12" md="4" v-for="(benefit, index) in [
          { icon: 'mdi-home', title: 'Quality projects', text: 'Institutional quality' },
          { icon: 'mdi-handshake', title: 'We make your investments easier', text: 'Backed by movable guarantees' },
          { icon: 'mdi-cash-multiple', title: 'Invest in the same way', text: 'To the global Real Estate funds' },
          { icon: 'mdi-cloud', title: 'We support you', text: 'In tangible assets' },
          { icon: 'mdi-wifi', title: '100% online', text: 'Save time and energy' },
          { icon: 'mdi-shield-check', title: 'Dont worry', text: 'We take care of the administrative procedures' }
        ]" :key="index">
          <v-card flat class="text-center pa-4">
            <v-icon size="40">{{ benefit.icon }}</v-icon>
            <h3 class="text-h6 font-weight-bold mt-2">{{ benefit.title }}</h3>
            <p class="text-subtitle-2">{{ benefit.text }}</p>
          </v-card>
        </v-col>
      </v-row>
    </v-container>

    <v-footer
    class="bg-grey-lighten-4 text-center d-flex flex-column"
  >
  
  <v-row justify="space-between" align="center" no-gutters>
  <!-- Links -->
  <v-col>
    <v-btn
      v-for="link in links"
      :key="link"
      class="mx-2"
      rounded="xl"
      variant="text"
    >
      {{ link }}
    </v-btn>
  </v-col>

  <!-- Caja de texto alineada a la derecha -->
  <v-col cols="12" sm="6" class="text-right">
    <v-textarea
      class="mx-2"
      label="your email"
      prepend-inner-icon="mdi-comment"
      rows="1"
    ></v-textarea>
  </v-col>
</v-row>

    

    <div>
      <v-btn
        v-for="icon in icons"
        :key="icon"
        :icon="icon"
        class="mx-4"
        variant="text"
      ></v-btn>
    </div>

    <v-divider></v-divider>

    <div>
      {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
    </div>
  </v-footer>
    

</v-container>
</template>

<style scoped>
.hero-section {
  background: linear-gradient(135deg, #5B46F2, #9069F2);
  padding: 100px 0;
  border-radius: 0 0 50px 50px;
}
.offer-section {
  padding: 50px 0;
}
.stats-section {
  background: #cacbcc;
  border-radius: 10px;
}
</style>