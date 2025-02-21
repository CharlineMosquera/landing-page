<script setup lang="ts">
import { ref, computed } from 'vue';
import { useRoute } from 'vue-router';

// Importar imágenes
import img1 from '@/assets/img/card1Blog.png';
import img2 from '@/assets/img/card2Blog.png';
import img3 from '@/assets/img/card3Blog.png';
import img4 from '@/assets/img/card4Blog.png';

// Lista de artículos
const items = ref([
  { id: 1, src: img1, category: 'Tech', tags: ['AI', 'Robotics', 'Innovation'], date: 'Feb 10, 2025', author: 'John Doe' },
  { id: 2, src: img2, category: 'Science', tags: ['Biology', 'Space', 'Research'], date: 'Feb 12, 2025', author: 'Jane Smith' },
  { id: 3, src: img3, category: 'Health', tags: ['Wellness', 'Fitness', 'Nutrition'], date: 'Feb 14, 2025', author: 'Emily Johnson' },
  { id: 4, src: img4, category: 'Business', tags: ['Marketing', 'Finance', 'Startups'], date: 'Feb 16, 2025', author: 'Michael Brown' }
]);

// Categorías y tags para el sidebar
const categories = ref([
  { name: 'Tech', count: 5 },
  { name: 'Science', count: 10 },
  { name: 'Health', count: 3 },
  { name: 'Business', count: 9 }
]);

const tags = ref(['AI', 'Robotics', 'Biology', 'Fitness', 'Finance']);

// Obtener la ruta actual
const route = useRoute();

// Buscar el artículo actual basado en la URL
const item = computed(() => items.value.find(i => i.id === parseInt(route.params.id)));
</script>

<template>
  <v-container class="d-flex">
    <!-- Sidebar -->
    <v-card class="pa-4 sidebar" width="250">
      <v-list>
        <v-list-subheader>Categories</v-list-subheader>
        <v-list-item v-for="(category, index) in categories" :key="index">
          <v-list-item-title>{{ category.name }}</v-list-item-title>
          <v-chip color="primary" size="small">{{ category.count }}</v-chip>
        </v-list-item>
      </v-list>

      <v-divider class="my-3"></v-divider>

      <v-list>
        <v-list-subheader>Tags</v-list-subheader>
        <v-chip v-for="(tag, index) in tags" :key="index" class="ma-1" color="grey">
          {{ tag }}
        </v-chip>
      </v-list>
    </v-card>

    <!-- Artículo -->
    <v-container v-if="item" class="ml-6 flex-grow-1">
      <v-card class="mx-auto" max-width="800">
        <v-img :src="item.src" height="400px" cover />
        <v-card-title class="text-center text-h5 font-weight-bold">
          {{ item.category }}
        </v-card-title>
        
        <v-card-subtitle class="text-center">
          <v-icon>mdi-account</v-icon> {{ item.author }} 
          <v-icon class="ml-2">mdi-calendar</v-icon> {{ item.date }}
        </v-card-subtitle>

        <v-card-text>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorem autem architecto consequuntur quasi id culpa. Omnis sint impedit odio, veritatis nobis perspiciatis recusandae, reprehenderit ea incidunt facere voluptatum quam consectetur.
        </v-card-text>

        <v-card-text class="text-center">
          <v-chip v-for="tag in item.tags" :key="tag" class="ma-1" color="primary" variant="outlined">
            {{ tag }}
          </v-chip>
        </v-card-text>
      </v-card>
    </v-container>
  </v-container>
</template>

<style scoped>
.sidebar {
  position: sticky;
  top: 20px;
  height: fit-content;
}
</style>
