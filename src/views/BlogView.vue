<script setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router';

// Importar imágenes
import img1 from '@/assets/img/card1Blog.png';
import img2 from '@/assets/img/card2Blog.png';
import img3 from '@/assets/img/card3Blog.png';
import img4 from '@/assets/img/card4Blog.png';
import img7 from '@/assets/img/headerGradiantBlog.png';

// Datos de los items
const items = ref([
  { id: 1, src: img1, category: 'Tech', tags: ['AI', 'Robotics', 'Innovation'] },
  { id: 2, src: img2, category: 'Science', tags: ['Biology', 'Space', 'Research'] },
  { id: 3, src: img3, category: 'Health', tags: ['Wellness', 'Fitness', 'Nutrition'] },
  { id: 4, src: img4, category: 'Business', tags: ['Marketing', 'Finance', 'Startups'] }
]);

const page = ref(1);
const router = useRouter();

// Redirigir al detalle
const goToDetail = (item) => {
  router.push({ name: 'BlogDetail', params: { id: item.id } });
};
</script>

<template>
  <v-container fluid class="pa-4">
    <v-img :src="img7" alt="Blog Header Image" height="300px" cover />
  </v-container>

  <v-card>
    <v-tabs bg-color="grey-lighten-4" center-active>
      <v-spacer></v-spacer>
      <v-tab>All</v-tab>
      <v-tab>Category 1</v-tab>
      <v-tab>Category 2</v-tab>
      <v-tab>Category 3</v-tab>
      <v-tab>Category 4</v-tab>
    </v-tabs>
  </v-card>

  <v-container class="pa-4">
    <v-row justify="center">
      <v-col v-for="item in items" :key="item.id" cols="12" sm="6" md="4">
        <v-card class="hover-card" @click="goToDetail(item)">
          <v-img :src="item.src" height="250px" cover />
          <v-card-title class="text-center">{{ item.category }}</v-card-title>
        </v-card>
      </v-col>
    </v-row>
  </v-container>

  <div class="text-center mt-6">
    <v-pagination v-model="page" :length="4" rounded="circle"></v-pagination>
  </div>
</template>

<style scoped>
.hover-card {
  cursor: pointer;
  transition: transform 0.3s ease;
}
.hover-card:hover {
  transform: scale(1.05);
}
</style>



