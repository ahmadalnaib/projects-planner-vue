<template>
  <div class="project">
    <div class="actions">
      <h3 @click="showDetails" title="show details">{{project.title}}</h3>
      <div class="icons">
       <i class="far fa-edit fa-2x"></i>
       <i class="far fa-trash-alt fa-2x"></i>
       <i class="far fa-check-circle fa-2x"></i>
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
  }
},
methods:{
  showDetails(){
    this.details=!this.details
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

