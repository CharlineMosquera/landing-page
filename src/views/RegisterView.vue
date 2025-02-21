<script setup lang="ts">
</script>

<template>
    <v-container fluid>
        <v-row>
            <v-col cols="12">
                <v-card>
                    <v-card-title>Register</v-card-title>
                    <v-card-text>
                        <v-form>
                            <v-text-field
                                v-model="email"
                                label="Email"
                                required
                            ></v-text-field>
                            <v-text-field
                                v-model="password"
                                label="Password"
                                required
                                type="password"
                            ></v-text-field>
                            <v-btn @click="register">Register</v-btn>
                        </v-form>
                    </v-card-text>
                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>