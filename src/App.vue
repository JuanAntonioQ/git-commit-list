<template>
  <div id="app">
    <BranchList/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import BranchList from './components/BranchList';

export default {
  name: 'App',
  components: {
    HelloWorld,
    BranchList,
  },
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
