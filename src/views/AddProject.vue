<template>
  <form  @submit.prevent="handleSubmit">
    <label>Title:</label>
    <input type="text" v-model="title" placeholder="Project Title" required />
    <label>Description:</label>
  <textarea type="text" v-model="details" placeholder="Project Description" required></textarea>
  <button>Add Project</button>
  </form>
</template>

<script>
export default {
 data(){
  return {
   title: '',
   description: ''
  }
 },
 methods:{
  handleSubmit(){

 
  console.log(this.title,this.details)
}
 }
}
</script>

<style>
form {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 50px;
  border: 1px solid #ccc;
  border-radius: 4px;
  background-color: #fff;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  margin-top: 20px;

}
label{
  margin-bottom: 10px;
  font-size: 16px;
  font-weight: bold;
  color: #333;
  text-align: left;
  text-transform: uppercase;
  letter-spacing: 1px;
  line-height: 24px;
  margin-bottom: 10px;
  margin-top: 10px;
  margin-left: 10px;
  margin-right: 10px;
  margin-bottom: 10px;
 

}
input {
  border: none ;
  border-radius: 4px;
  padding: 10px;
  margin-bottom: 10px;
  margin-top: 10px;
  margin-left: 10px;
  margin-right: 10px;
  margin-bottom: 10px;
  font-size: 16px;
  font-weight: bold;
  color: #333;
  text-align: left;
  text-transform: uppercase;
  letter-spacing: 1px;
  line-height: 24px;
}
textarea{
  border: none;
  border-radius: 4px;
  padding: 10px;
  margin-bottom: 10px;
  margin-top: 10px;
  margin-left: 10px;
  margin-right: 10px;
  margin-bottom: 10px;
  font-size: 16px;
  font-weight: bold;
  color: #333;
  text-align: left;
  text-transform: uppercase;
  letter-spacing: 1px;
  line-height: 24px;
  outline: none;
}
button{
  border-radius: 5px;
  padding: 10px;
  margin-bottom: 10px;
  margin-top: 10px;
  margin-left: 10px;
  margin-right: 10px;
  margin-bottom: 10px;
  font-size: 16px;
  font-weight: bold;
  color: white;
  text-align: left;
  text-transform: uppercase;
  letter-spacing: 1px;
  line-height: 24px;
  cursor: pointer;
  transition: all 0.3s ease-in-out;
  background-color: #333;
  border: 1px solid #333;
  border-radius: 4px;
  outline: none;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
 
}
button:hover{
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.3), 0 6px 20px 0 rgba(0, 0, 0, 0.22);
  transition: all 0.3s ease-in-out;
  background-color: #620ab5;
}

</style>  