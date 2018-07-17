<template>
  <div class="branch-list-wrapper">
    <ul>
      <div class="checkbox-container" v-for="branch in braches" :key="branch.name">
        <input type="checkbox">  
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



