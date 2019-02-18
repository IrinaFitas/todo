<template>
	<div id="app">
		<app-list></app-list>
	</div>
</template>

<script>
import List from "./components/List.vue";
export default {
  components: {
    appList: List
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: red;
}
</style>
