<template>
  <div class="Team">
    <h1 class="v-subheader grey--text display-1">Our Team</h1>
    <v-container class="ma-10">
      <v-layout row wrap>
        <v-flex xs12 sm6 md4 lg3 v-for="person in team" :key="person.name">
          <v-card flat class="text-center ma-5 lighten-2" color="grey">
            <v-responsive class="pt-6">
              <v-avatar size="250" class="grey lighten-2">
                <v-img :src="person.avatar" :lazy-src="person.avatar"></v-img>
              </v-avatar>
            </v-responsive>
            <v-card-text>
              <div class="v-subheader font-weight-bold darken-4">{{ person.name }}</div>
              <div color="grey--text">{{ person.role }}</div>
            </v-card-text>
            <v-card-actions class="justify-center ">
              <v-btn class="v-btn--flat lighten-1 " small color="grey" >
                <v-icon small left>mdi-message</v-icon>
                <span>Message</span>
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-layout>
   </v-container>
  </div>
</template>
<script>

export default {
  data(){
    return{
      team:[
        { name: 'Mihai', role:'Full stack developer', avatar: require('@/assets/avatar/1-avatar.jpg')},
        { name: 'Alexandra', role: 'Front end developer', avatar:require('@/assets/avatar/2-avatar.jpg')},
        { name: 'Cristi', role: 'Team mentor', avatar:require('@/assets/avatar/3-avatar.jpg')},
        { name: 'Bogdan', role: 'Back end developer', avatar:require('@/assets/avatar/4-avatar.jpg')}
      ]
    }
  }
}

</script>
<style>

</style>

