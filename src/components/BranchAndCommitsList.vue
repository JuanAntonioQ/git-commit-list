<template>
  <div class="todoList">
    <h1>{{ msg }}</h1>
    <BranchList @branchSelected="branchChanged"/>
    <CommitList :branchSelected="branchSelected" />    
  </div>
</template>

<script>

import axios from 'axios'
import BranchList from "./BranchList"
import CommitList from "./CommitList"

export default {
  name: 'BranchAndCommitsList',
  components: {
    BranchList,
    CommitList,
  },
  data() {
    return {
        msg: 'Latest todo-list yunior commits',
        branchSelected : '',
        newTodo : {
            text: '',
            createdAt: Date.now(),
            isCompleted : false
        }
    };
  },
  methods: {
      branchChanged(branchSelected){
        this.branchSelected = branchSelected;
      }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
