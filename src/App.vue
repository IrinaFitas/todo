<template>
	<div id="app">
		<app-input-item></app-input-item>
		<app-list></app-list>
	</div>
</template>

<script>
import List from "./components/List.vue";
import InputItem from "./components/Input-item.vue";
export default {
  components: {
	appList: List,
	appInputItem: InputItem
  }
}
</script>

<style>
#app {
	display: flex;
	margin: auto;
	flex-direction: column;
	justify-content: center;
	font-family: 'Avenir', Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
	border: 2px solid black;
	width: 85%;
}
</style>
