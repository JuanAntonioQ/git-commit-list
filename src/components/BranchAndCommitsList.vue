<template>
  <div class="todoList">
    <h1>{{ msg }}</h1>
    <BranchList :branches="branches"/>
    
    

  </div>
</template>

<script>

import axios from 'axios'
import BranchList from "./BranchList"

export default {
  name: 'BranchAndCommitsList',
  components: {
    BranchList,
  },
  data() {
    return {
        msg: 'Latest todo-list yunior commits',
        branches: [],
        newTodo : {
            text: '',
            createdAt: Date.now(),
            isCompleted : false
        }
    };
  },
  methods: {
      loadData() {
          axios.get("https://api.github.com/repos/JuanAntonioQ/KataPotter/branches?access_token=f7116094ddd78181389ce891bafa9226aebba179")
          .then(response => this.branches = response.data);
      },
  },
  created() {
      this.loadData()
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
