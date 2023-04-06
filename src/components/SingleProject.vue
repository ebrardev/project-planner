<template>
  <div class="project">
    <div class="actions">
     <h3  @click="showDetails =!showDetails" >{{ project.title }}</h3>
     <div class="icons">
        <span class="material-icons">edit</span>
        <span @click="deleteProject" class="material-icons">delete</span>
        <span class="material-icons">done</span>
     </div>

    </div>
    <div class="details"  v-if="showDetails">
        <p>{{ project.details }}</p>
    </div>
  </div>
</template>

<script>
export default {
    props: ['project'],
    data() {
        return{
            showDetails: false,
            uri: 'http://localhost:3000/projects/'+this.project.id
        }
    },
    methods:{
        deleteProject(){
            fetch(this.uri,{
                method: 'DELETE'   })
                .then(()=>this.$emit('delete',this.project.id))
         
        },
    },
    

}
</script>

<style>
.project{
    margin: 20px auto;
    padding: 20px;
    border-radius: 10px;
    background-color: #fff;
    box-shadow: 0 10px 20px rgba(0,0,0,0.19);
    border: 1px solid #eee;
    box-sizing: border-box;
    transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
    cursor: pointer;
    border-left: 4px solid green;
}
h3{
    font-size: 20px;
    margin-bottom: 10px;
    font-weight: bold;
    text-align: center;
    color: #333;
    transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
    cursor: pointer;
}
.actions{
    display: flex;
    justify-content:space-between;
    align-items: center;
}
.icons{
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100px;
}
.material-icons{
    font-size: 22px;
    color: #27ae60;
    cursor: pointer;
    margin-left: 10px;
    transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);

}
.material-icons:hover{
    color: #e74c3c;
}
</style>