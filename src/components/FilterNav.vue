<template>
  <nav class="filter-nav">
     <button 
     @click="updateFilter('all')"
     :class="{active:current ==='all'}"
     >view All
     </button>

        <button 
     @click="updateFilter('completed')"
      :class="{active:current ==='completed'}"
     >Completed
     </button>

        <button 
     @click="updateFilter('ongoing')"
      :class="{active:current ==='ongoing'}"
     >On Going
     </button>
  </nav>
</template>

<script>
export default {
  props:['current'],
methods:{
  updateFilter(by){
       this.$emit('filterChange',by)
  }
}
}
</script>

<style scoped>

.filter-nav button {
  background: none;
  border: none;
  color: #bbb;
  outline: none;
  font-size: 12px;
  text-transform: uppercase;
  margin-top: 2rem;
  margin-left: 10px;
  letter-spacing: 1px;
  font-weight: bold;
  cursor: pointer;
}

.filter-nav button.active {
  color: rgb(30, 128, 167);
}
</style>