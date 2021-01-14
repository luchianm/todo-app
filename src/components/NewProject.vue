<template>
  <v-dialog max-width="600px" class="justify-center">
    <template v-slot:activator="{on,attrs}">
      <v-btn small v-on="on" v-bind="attrs" class="success">Add new project</v-btn>
    </template>
    <v-card>
      <v-card-title>
        <v-card-title>
          <h2>Add New Project</h2>
        </v-card-title>
        <v-card-text>
          <v-form ref="form">
            <v-text-field :value="due" label="Title" v-model="title" prepend-icon="mdi-folder" :rules="inputRules"></v-text-field>
            <v-textarea label="Information" v-model="content" prepend-icon="mdi-pencil" :rules="inputRules"></v-textarea>
            <v-menu class="align-content-center">
              <template v-slot:activator="{ on,attrs }">
                <v-text-field v-bind="attrs" v-on="on" label="Due date" prepend-icon="mdi-calendar-range" :value="due" :rules="inputRules"></v-text-field>
              </template>
              <v-date-picker
                  v-model="due"
                  color="green lighten-1"
              ></v-date-picker>
            </v-menu>
            <v-spacer></v-spacer>
            <v-btn success class="mx-0 mt-3 v-btn--flat" @click="submit" color="grey">Add project</v-btn>
          </v-form>
        </v-card-text>
      </v-card-title>
    </v-card>
  </v-dialog>
</template>
<script>
import format from 'date-fns/format';

export default {
  data(){
    return{
      title: '',
      content: '',
      due: '',
      inputRules: [
          v => v.length >= 3 || 'Minimum length is 3 characters'
      ]
    }
  },
  methods:{
    submit(){
      if(this.$refs.form.validate()){
        console.log(this.title,this.content,this.due);
      }

    }
  },
  computed:{
    formattedDate(){
      return this.due ? format(this.due,"DD MM YYYY") : '';
    }
  }
}
</script>
<style>

</style>
