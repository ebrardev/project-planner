<template>
  <div class="home">
   <div v-if="projects.length">
    <div v-for="project in projects" :key="project.id">
       
    <SingleProject :project="project" @delete="handleDelete" />
    
    </div>

   </div>
  </div>
</template>

<script>
// @ is an alias to /src

import axios from 'axios';
import SingleProject from '../components/SingleProject.vue';

export default {
  name: 'HomeView',
  components: {
    SingleProject

  },
  data(){
    return {
      projects:[]
  }
},
  mounted(){
  
    axios.get('http://localhost:3000/projects')
  .then(response => {
    this.projects = response.data;
  })
  .catch(error => {
    console.log(error.message);
  });
  },
  methods:{
    handleDelete(id){
      this.projects = this.projects.filter((project) => project.id !== id);
    }
  }
}
</script>


