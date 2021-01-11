<template>
  <div class="Dashboard ma-1">
    <h1 class="subheading grey--text display-1">Dashboard</h1>
    <v-container class="ma-10">
      <v-card flat class="pa-3 grey lighten-4" v-for="project in projects" :key="project.title">
        <v-layout row wrap :class="`pa-3 project ${project.status}`">
          <v-flex xs12 md6>
            <div class="caption grey--text font-weight-bold text--darken-1">Project title</div>
            <div>{{ project.title }}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text font-weight-bold text--darken-1">Person</div>
            <div>{{ project.person }}</div>
          </v-flex >
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text font-weight-bold text--darken-1">Due by</div>
            <div>{{ project.due }}</div>
          </v-flex>
          <v-flex xs2 sm4 md2>
            <div>
              <v-chip :class="`${project.status} white--text caption my-2`" :color="`${project.status}`" small>{{project.status}}</v-chip>
            </div>
          </v-flex>

        </v-layout>
        <v-divider class="mt-4"></v-divider>
      </v-card>

    </v-container>
  </div>
</template>

<script>


export default {
  data (){
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
  methods:{
    color(prop){
      if (prop.status ==='complete'){
        return('success');
      }
      else if (prop.status ==='ongoing'){
        return('orange');
      }
      else
        return('tomato');
    }
  }
}
</script>

<style>

.project.complete{
  border-left: 4px solid #3cd1c2;
}
.project.ongoing{
  border-left: 4px solid orange;
}
.project.overdue{
  border-left: 4px solid tomato;
}
.v-chip.complete{
  background: #3cd1c2;
}
.v-chip.ongoing{
  background: orange;
}
.v-chip.overdue{
  background: tomato;
}
</style>
