<template>
  <v-app class="grey lighten-2">
    <NavBar/>
    <v-content class="mx-8 mt-8">
      <router-view></router-view>

    </v-content>
  </v-app>
</template>

<script>
import NavBar from '@/components/NavBar';


export default {
  name: 'App',

  components:{
    NavBar
  },

  data: () => ({
  }),
};
</script>
