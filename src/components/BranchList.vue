<template>
  <div class="branch-list-wrapper">
    <ul>
      <div class="checkbox-container">
        <input type="checkbox" v-for="branch in braches" :key="branch.name">  
        <label>{{branch.name}}</label>
      </div>
    </ul>
  </div>  
</template>

<script>
export default {
  name: 'BranchList',
  props: [ 'branches' ],
  data(){
    return {

    }
  }
  
}
</script>

<style>

</style>



