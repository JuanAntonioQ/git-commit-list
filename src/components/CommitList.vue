<template>
  <div class="commit-list-wrapper">
    <p class="branch-path">Usuario/nombre-repo@</p>
    <ul>
      <li v-for="(commit, idx) in commits" :key="idx">
        <p>{{commit.commit.message}}</p>
      </li>
    </ul>
  </div>  
</template>

<script>

import axios from 'axios';

export default {
  name: 'CommitList',
  props: [ 'branchSelected'],
  data(){
    return {
      commits : [],
    }
  },
  methods : {
    loadCommitsFromBranch(){
      const urlBase = 'https://api.github.com/repos/JuanAntonioQ/git-commit-list/commits';
      const token = '?access_token=9a87d24bb9f3e2e4cbe48642be0eba1c17cced36';
      const branchName = '&sha=' + this.branchSelected;
      axios.get(urlBase + token + branchName)
        .then(response => {
          console.log('Peticion resuelta con: ', response.data);
          this.commits = response.data;
        }).catch(error => {
          console.log('Error en la peticion de commit por rama');
        })
    }
  },
  created(){
    this.loadCommitsFromBranch();
  }
  ,
  watch : {
    branchSelected(){
      this.loadCommitsFromBranch();
    }
  }
  
  
}
</script>

<style>


</style>



