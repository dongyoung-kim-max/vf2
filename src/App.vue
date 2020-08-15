<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <v-app-bar-nav-icon @click="drawer = !drawer" />
      <site-title :title="title"></site-title>
      <v-spacer/>
      <v-btn icon to="/about">
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
      <v-btn icon to="/">
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
    </v-app-bar>
    <v-navigation-drawer app v-model="drawer">

      <v-divider></v-divider>
      <site-menu></site-menu>
    </v-navigation-drawer>
    <v-content>
      <router-view/>
    </v-content>
    <site-footer :footer='footer'></site-footer>
  </v-app>
</template>

<script>
import SiteTitle from '@/components/title'
import SiteFooter from '@/components/footer'
import SiteMenu from '@/components/menu'

export default {
  components: { SiteTitle, SiteFooter, SiteMenu },
  name: 'App',
  data () {
    return {
      drawer: false,
      title: '안녕 디스코드',
      footer: '힘들다.'
    }
  }
}
</script>
