<template>
  <form  @submit.prevent="handelSubmit">
    
    <label for="title">Title</label>
    <input type="text" required v-model="title">

        <label for="details">Details</label>
         <textarea  required v-model="deatils"></textarea>
         <button>Add project</button>
  </form>
</template>

<script>
export default {
data(){
  return {
    title:'',
    details:'',
  }
},
methods:{
  handelSubmit(){
    alert(this.title)
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