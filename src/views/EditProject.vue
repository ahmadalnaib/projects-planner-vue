<template>
  <form  @submit.prevent="handelSubmit">
    
    <label for="title">Title</label>
    <input type="text" required v-model="title">

        <label for="details">Details</label>
         <textarea  required v-model="details"></textarea>
         <button>Update project</button>
  </form>
</template>

<script>
export default {
  props:['id'],
data(){
  return {
    title:'',
    details:'',
    url:'http://localhost:3000/projects/'+ this.id,
  }
},

mounted(){
fetch(this.url)
.then(res =>res.json())
.then(data =>{
 this.title=data.title
 this.details=data.details
})
},
methods:{
handelSubmit(){
   fetch(this.url,{
     method:'put',
     headers:{'Content-type':'application/json'},
     body:JSON.stringify({title:this.title,details:this.details})
   }).then(()=>{
     this.$router.push('/')
   })
  }
}
}
</script>

<style  scoped>

form {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
margin-top: 10rem;
  border-radius:10px ;
  padding: 20px;
  max-width: 600px;
  margin: 0 auto; 
  

}
input,textarea {
  padding: 1rem;
  border-radius:5px ;
  border: none;
  width: 100%;
  margin: 10px;
}



input:focus,
textarea:focus
{
  outline: none;
}

label {
  color: aqua;
  display: block;
  text-transform: uppercase;
}

button {
  border: none;
  background: #00ce89;
  color: #fff;
  margin-top: 10px;
  padding: 1rem;
  cursor: pointer;
  border-radius: 6px;
  font-size: 16px;
}
</style>