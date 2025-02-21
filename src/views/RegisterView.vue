<script setup lang="ts">
import { ref } from 'vue'
import { useAuthStore } from '../stores/authStore'

const name = ref('')
const email = ref('')
const password = ref('')

const { register } = useAuthStore()

const handlerRegister = async () => {
  try {
    await register(name.value, email.value, password.value)
    alert('Registration successful')
  } catch (error) {
    console.error('Error al registrar usuario:', error.message)
    alert('Registration failed')
  }
}
</script>

<template>
  <div>
    <form @submit.prevent="handlerRegister">
      <input
        type="text"
        minlength="3"
        maxlength="100"
        placeholder="Nombre"
        v-model="name"
        required
      />
      <input type="email" placeholder="Correo" v-model="email" required />
      <input
        type="password"
        minlength="6"
        maxlength="12"
        placeholder="Contraseña"
        v-model="password"
        required
      />
      <button type="submit">Registrar</button>
    </form>
  </div>
</template>

<style></style>
