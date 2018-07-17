<template>
  <div class="branch-list-wrapper">
    <ul>
      <div class="checkbox-container" v-for="branch in branches" :key="branch.name">
        <input @click="comunnicateBranchChanged(branch.name)" type="radio">  
        <label>{{branch.name}}</label>
      </div>
    </ul>

  </div>  
</template>

<script>
import axios from 'axios';

export default {
  name: 'BranchList',
  
  data(){
    return {
      branches: [],
    }
  },
  methods : {
    comunnicateBranchChanged(branchSelected){
      this.$emit('branchSelected', branchSelected);
    },
    loadData() {
      axios.get("https://api.github.com/repos/JuanAntonioQ/git-commit-list/branches?access_token=9a87d24bb9f3e2e4cbe48642be0eba1c17cced36")
      .then(response => this.branches = response.data);
    },
  },
  
  created() {
      this.loadData()
  }
}
</script>

<style>

.checkbox-container{
  display: inline-block;
  margin-right: 10px;
}
.checkbox-container:last-child{
  margin-right: 0;
}

ul li{
  list-style-type: none;
}

</style>



