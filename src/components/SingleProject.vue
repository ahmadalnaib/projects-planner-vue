<template>
  <div class="project" :class="{complete:project.complete}">
    <div class="actions">
      <h3 @click="showDetails" title="show details">{{project.title}}</h3>
      <div class="icons">
       <i class="far fa-edit fa-2x"></i>
       <i @click="deleteProject" class="far fa-trash-alt fa-2x"></i>
       <i @click="toggleComplete" class="far fa-check-circle fa-2x tick"></i>
      </div>
    </div>
    <div v-if="details" class="details">
      <p>{{project.details}}</p>
    </div>
  </div>
</template>

<script>
export default {
props:['project'],

data(){
  return {
    details:false,
    url:'http://localhost:3000/projects/' +this.project.id,
  }
},
methods:{
  showDetails(){
    this.details=!this.details
  },
  deleteProject(){
    fetch(this.url,{method:"DELETE"})
    .then(() => this.$emit('delete',this.project.id))
    .catch(err => console.log(err.message))
    
  },
  toggleComplete()
  {
    fetch(this.url,{
      method:"PUT",
      headers:{'Content-type':'application/json'},
      body:JSON.stringify({complete:!this.project.complete})
      }).then(()=>{
        this.$emit('complete',this.project.id)
        .catch(err => console.log(err.message))
      })

  }
}
}
</script>

<style  scoped>
.project {
  margin: 20px auto;
  background: #fff;
  padding: 10px 20px;
  border-radius: 4px;
  box-shadow: 1px 2px 3px rgb(0, 0, 0,0.05);
  border-left: 4px solid #e90074;
}
.complete{
  border-left:4px solid #00ce89 ;
}

.project.complete .tick {
  color: #00ce89;
}
h3 {
  cursor: pointer;
}

.actions{
  display: flex;
  justify-content: space-around;
  align-content: center;
  align-items: center;
  padding: 1rem;
}

.icons i{
 margin: 0.20rem;
 cursor: pointer;
 color: #bbb;
 
}

.icons i:hover{
  color: #777;
  transition: all 1s ease;
}
</style>

