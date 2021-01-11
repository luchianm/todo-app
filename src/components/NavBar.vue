<template>
  <nav>
    <v-app-bar app flat color="grey" class="lighten-1">
        <v-app-bar-nav-icon class="grey--text" @click="drawer = !drawer"></v-app-bar-nav-icon>
        <v-toolbar-title class="text-uppercase grey--text display-2">
          <span class="font-weight-light">
            ToDo
          </span>
          <span class="font-weight-bold">
            List
          </span>
        </v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn flat color="grey" class="lighten-2">
          <span class="grey--text ">Sign Out</span>
          <v-icon color="grey" right>mdi-logout</v-icon>
        </v-btn>
    </v-app-bar>
    <v-navigation-drawer app hide-overlay class="primary" v-model="drawer">
      <v-list>
        <v-list-item-title>
          <v-list-item-group >
            <v-list-item v-for="link in links" :key="link.text" router :to="link.route">
              <v-list-item-icon>
                <v-icon color="white">{{ link.icon }}</v-icon>
              </v-list-item-icon>
              <v-list-item-action class="white--text">
                {{ link.text }}
              </v-list-item-action>
            </v-list-item>

          </v-list-item-group>
        </v-list-item-title>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>
<script>

export default {
  data(){
    return{
      drawer: false,
      links: [
        {
          icon: 'mdi-view-dashboard',
          text: 'Dashboard',
          route: '/'
        },
        {
          icon: 'mdi-folder',
          text: 'My Projects',
          route: '/projects'
        },
        {
          icon: 'mdi-account-group',
          text: 'Team',
          route: '/team'
        }

      ]
    }
  }
}
</script>
<style>

</style>