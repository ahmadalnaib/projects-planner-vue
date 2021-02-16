<template>
  <div class="project">
    <div class="actions">
      <h3 @click="showDetails" title="show details">{{project.title}}</h3>
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
</style>

