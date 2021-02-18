<template>
  <nav class="navbar">
    <router-link :to="{name:'Home'}">Projects</router-link>
      <router-link :to="{name:'AddProject'}">Add a New Project</router-link>
  </nav>
</template>

<script>
export default {

}
</script>

<style  scoped>
.navbar {
  display: flex;
  justify-content: space-around;
  background: #fff;
  color: #333;
  padding: 1rem;
 
}
a {
  text-decoration: none;
  color: #00ce89;
  
}

a.router-link-active{
  border-bottom: 2px solid #e90074;
  padding-bottom:4px ;
}


</style>

