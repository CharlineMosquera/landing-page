<script setup lang="ts">
</script>
<template>
   <v-app>
        <v-container fluid class=" fill-height d-flex align-center justify-center">
            <v-row no-gutters class="fill-height">
                <v-col cols="12" md="6" class="d-none d-md-flex">
                    <v-img
                        src="../../src/assets/img/login.png"
                        class="fill-height"
                        cover
                    >
                    </v-img>
                </v-col>
                <v-col cols="12" md="6" class="d-flex align-center justify-center fill-height">
                    <!--Formulario para Login-->
                    <v-card class="elevation-2 pa-8 fill-height d-flex flex-column align-center justify-center" width="800">

                        <v-card-title 
                            class="text-h5 mb-4"
                            >Hello again !!
                        </v-card-title>

                        <v-card-subtitle class="text-body-1 mb-6">
                            Don't have an account yet? <a href="/register" class="text-blue-500">Sign up</a>
                        </v-card-subtitle>
                    
                        <v-card-text>
                            <v-form>
                                <v-text-field
                                    v-model="email"
                                    label="Your email"
                                    prepend-icon="mdi-email"
                                    type="email"
                                    outlined
                                    dense
                                    class="mb-4"
                                    required
                                ></v-text-field>
                                <v-text-field
                                    v-model="password"
                                    label="Your password"
                                    prepend-icon="mdi-lock"
                                    type="password"
                                    outlined
                                    dense
                                    class="mb-4"
                                    required
                                ></v-text-field>
                                <v-row class="mb-4">
                                    <v-col cols="6">
                                        <v-checkbox
                                            v-model="rememberMe"
                                            label="Remember me"
                                            hide-details
                                            class="mt-0"
                                        ></v-checkbox>
                                    </v-col>
                                    <v-col cols="6" class="text-right">
                                        <!-- Pendiente de redirigir al usuario en caso de que no recuerde la contraseña-->
                                        <a href="#" class="text-blue-500">Forgot password?</a>
                                    </v-col>
                                </v-row>
                                <v-btn
                                    block
                                    color="black"
                                    dark
                                    large
                                    class="mb-4"
                                >
                                    Login
                                </v-btn>
                            </v-form>
                        </v-card-text>
                    </v-card>
                </v-col>
            </v-row>
        </v-container>             
   </v-app>
</template>

<script lang="ts">
export default {
    data() {
        return {
            email: '',
            password: '',
            rememberMe: false,
        }
    },
}
</script>

<style scoped>
.text-blue-500 {
    color: #1e40af;
}
.fill-height {
    height: 100vh;
    width: 100%;
}
</style>