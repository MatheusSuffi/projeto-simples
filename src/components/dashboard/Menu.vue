<template>
    <v-navigation-drawer class="gray" dark app>
        <v-sheet color="gray" class="pa-4" >
            <div>Olá {{nomeUser}}</div>
        </v-sheet>

        <v-divider />
            <v-list>
                <v-list-item v-for="item in dashboard" :key="item.title" link @click="$router.push({ path: '/' })">
                    <v-list-item-icon>
                        <v-icon>{{ item.icon }}</v-icon>
                    </v-list-item-icon>

                    <v-list-item-content>
                        <v-list-item-title>{{ item.title }}</v-list-item-title>
                    </v-list-item-content>
                  </v-list-item>
            </v-list>
            <v-list>
                <v-list-group v-for="item in itemsMenu" :key="item.title" v-model="item.active" :prepend-icon="item.action" no-action>
                    <template v-slot:activator>
                        <v-list-item-content>
                            <v-list-item-title v-text="item.title"></v-list-item-title>
                        </v-list-item-content>
                    </template>

                    <v-list-item v-for="child in item.items" :key="child.title" link @click="$router.push({ path: child.to })" >
                        <v-list-item-content>
                            <v-list-item-title>{{ child.title }}</v-list-item-title>
                        </v-list-item-content>
                    </v-list-item>
                </v-list-group>
          </v-list>
      

        <template v-slot:append>
            <div class="pa-2">
              <v-btn block>
                  <v-icon left dark >
                      mdi-account
                  </v-icon>
                  Perfil
              </v-btn>
            </div>
            <div class="pa-2">
                <v-btn @click="logout" block>
                    <v-icon left dark >
                        mdi-logout
                    </v-icon>
                    Logout
                </v-btn>
            </div>
        </template>
    </v-navigation-drawer>
</template>

<script>
    export default {
        data () {
            return {
                nomeUser: '',
                dashboard: [
                    { title: 'Dashboard', icon: 'mdi-view-dashboard', to: '/' },
                ],itemsMenu: [{
                    ordem:"1.0",
                    title: "Menu 1",
                    action:"mdi-account",
                    permissao:"Menu 1 ",
                    items:[{
                        title:"Submenu 1 ",
                        to:"/"
                    }],
                }]
            }
        },
        methods: {
            async logout() {
                this.$router.push({ path: '/login' })   
            }
        },
        mounted() {
        },
        created(){
            console.log('menu chamado no created')
        }
    }
</script>

<style>

</style>