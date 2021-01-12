<template>
  <div class="Projects">
    <h1 class="subheading grey--text display-1">Projects</h1>
    <v-container class="ma-10">
      <v-row justify="center">
        <v-expansion-panels>
          <v-expansion-panel class="grey lighten-4 my-2" v-for="project in myProjects" :key="project.title">
            <v-expansion-panel-header>{{project.title}}</v-expansion-panel-header>
            <v-expansion-panel-content>
              <v-card class="grey lighten-3 px-6 grey--text py-4">
                <div>due by <strong class="darken-2">{{project.due}}</strong></div>
                <div class="darken-1">{{project.content}}</div>
              </v-card>
            </v-expansion-panel-content>
          </v-expansion-panel>
        </v-expansion-panels>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data(){
    return{
      projects:[
        {
          title:'First website',
          person:'Mihai',
          due:'1st Jan 2021',
          status:'complete',
          content:'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Beatae, commodi, corporis deleniti distinctio dolorum ea fugiat id illo libero maiores minus nam nisi odit perspiciatis reiciendis tempore ullam velit veritatis!'
        },
        {
          title:'Frontend',
          person:'Alexandra',
          due:'30th Jan 2021',
          status: 'ongoing',
          content: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Beatae, commodi, corporis deleniti distinctio dolorum ea fugiat id illo libero maiores minus nam nisi odit perspiciatis reiciendis tempore ullam velit veritatis!'
        },
        {
          title:'Backend',
          person:'Mihai',
          due:'20th Jan 2021',
          status: 'overdue',
          content: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Beatae, commodi, corporis deleniti distinctio dolorum ea fugiat id illo libero maiores minus nam nisi odit perspiciatis reiciendis tempore ullam velit veritatis!'
        },
        {
          title:'Server deploy',
          person:'Mihai',
          due:'25th Jan 2021',
          status: 'ongoing',
          content: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Beatae, commodi, corporis deleniti distinctio dolorum ea fugiat id illo libero maiores minus nam nisi odit perspiciatis reiciendis tempore ullam velit veritatis!'
        }
      ]
    }
  },
  computed:{
    myProjects() {
      return this.projects.filter(project => {
        return project.person === 'Mihai'
      });
    }
  }

}
</script>

<style>

</style>
