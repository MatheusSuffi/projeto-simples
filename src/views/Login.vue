<template>
    <v-app id="inspire">
        <v-content>
            <v-container fluid fill-height>
                <v-layout align-center justify-center>
                    <v-snackbar v-model="snackbar"  :timeout="timeout" >
                        {{ textSnackbar }}
                        <template v-slot:action="{ attrs }">
                            <v-btn color="blue" text v-bind="attrs" @click="snackbar = false"> FECHAR </v-btn>
                        </template>
                    </v-snackbar>
                    <v-flex xs12 sm8 md4>
                        <v-card class="elevation-12">
                        <v-toolbar dark color="primary">
                            <v-toolbar-title>Login</v-toolbar-title>
                        </v-toolbar>
                        <v-card-text>
                            <v-form>
                                <v-text-field
                                    prepend-icon="mdi-account"
                                    name="login"
                                    label="E-Mail"
                                    type="text"
                                    v-model="usuario"
                                ></v-text-field>
                                <v-text-field
                                    id="password"
                                    prepend-icon="mdi-lock"
                                    name="password"
                                    label="Senha"
                                    type="password"
                                    v-model="senha"
                                ></v-text-field>
                            </v-form>
                        </v-card-text>
                        <v-card-actions>
                            <v-spacer></v-spacer>
                            <v-btn color="primary" @click="login">Login</v-btn>
                        </v-card-actions>
                        </v-card>
                    </v-flex>
                    <v-overlay :value="overlay">
                        <v-progress-circular
                            indeterminate
                            size="64"
                        ></v-progress-circular>
                    </v-overlay>
                </v-layout>
            </v-container>
        </v-content>
    </v-app>
</template>

<script>
export default {
    name: 'Login',
    data: () => ({
      overlay: false,
      snackbar: false,
      textSnackbar: '',
      timeout: 3000,
      usuario: '',
      senha: ''
    }),

    props: {
        source: String,
        logout: String
    },

    methods:{
        async login(){
            this.$router.push({ path: '/' })
        }
    }
};
</script>

<style></style>
