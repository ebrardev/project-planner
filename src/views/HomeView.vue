<template>
  <div class="home">
   <div v-if="projects.length">
    <div v-for="project in projects" :key="project.id">
       <p>{{ project.title }}</p>
    
    
    </div>

   </div>
  </div>
</template>

<script>
// @ is an alias to /src

import axios from 'axios';

export default {
  name: 'HomeView',
  components: {

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
  }
}
</script>


