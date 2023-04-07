<template>
  <div class="home">
    <FilterNav  @filterChange="current=$event" :current="current"/> 
   <div v-if="projects.length">
    <div v-for="project in projects" :key="project.id">
       
    <SingleProject
     :project="project" 
     @delete="handleDelete"
     @complete="handleComplete"
     
     />
    
    </div>

   </div>
  </div>
</template>

<script>
// @ is an alias to /src

import axios from 'axios';
import SingleProject from '../components/SingleProject.vue';
import FilterNav from '../components/FilterNav.vue';

export default {
  name: 'HomeView',
  components: {
    SingleProject,
    FilterNav

  },
  data(){
    return {
      projects:[],
      current:'all'
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
    },
    handleComplete(id){
      let p=this.projects.find(project=>project.id===id)
      p.complete = !p.complete
    }
  }
}
</script>


