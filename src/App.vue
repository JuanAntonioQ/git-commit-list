<template>
  <div id="app">
    <BranchAndCommitsList/>
  </div>
</template>

<script>

import HelloWorld from './components/HelloWorld';
import BranchAndCommitsList from './components/BranchAndCommitsList';

export default {
  name: 'App',
  components: {
    HelloWorld,
    BranchAndCommitsList,
  },
  data(){
    return {
      
    }
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
