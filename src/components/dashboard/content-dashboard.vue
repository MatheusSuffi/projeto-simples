<template >  
	<v-flex class="pr-3 pb-3" xs12 md12 lg12>
        <v-card elevation="10">
        <v-card-title>
            <v-icon large left>
                mdi-cog
            </v-icon>
            <span class="title font-weight-light">Configuração Rápida</span>
        </v-card-title>
        <v-card-subtitle>
            <span class="subtitle font-weight-light">Acesse as principais funções rapidamente</span>
        </v-card-subtitle>

        <v-card-text class="headline font-weight-bold">
            <v-btn  color="blue" class="ma-2 white--text">
                <v-icon
                    left
                    dark
                >
                    mdi-account
                </v-icon>
                Perfil
            </v-btn>
        </v-card-text>
        </v-card>
        <p />
        <v-row>
        </v-row>
    </v-flex>
</template>

<script>
    //Graficos - Importação

    //import axios from 'axios'
    export default {
        components: {   },
        data: () => {
            return {
            chartOptions: {
                hoverBorderWidth: 20
            },
            chartData: {
                hoverBackgroundColor: "red",
                hoverBorderWidth: 10,
                labels: ["Green", "Red", "Blue"],
                datasets: [
                {
                    label: "Data One",
                    backgroundColor: ["#41B883", "#E46651", "#00D8FF"],
                    data: [1, 10, 5]
                }
                ]
            }
            };
        },
        mounted(){

        }

    }
</script>

<style scoped>
.v-input {
    font-size: 1.2em;
}

</style>