<template>
    <v-app id="inspire">
        <!--Header da pagina !-->
        <Header />
        <!--Menu da pagina !-->
        <Menu />
        <!--Corpo da pagina !-->
        <p></p>
        <ContentDashBoard />
    </v-app>
</template>

<script>
    import Header from '@/components/dashboard/Header.vue'
    import Menu from '@/components/dashboard/Menu.vue'
    import ContentDashBoard from '@/components/dashboard/content-dashboard.vue'

    export default {
        components : { Menu, ContentDashBoard, Header },
    }
</script>