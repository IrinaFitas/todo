<template>
	<div id="app">
		<app-input-item @addedTask="addedTask"></app-input-item>
		<app-list :list="taskArray" @idWasPassed="passedId" @deleteTaskId="deleteTask"></app-list>
	</div>
</template>

<script>
import List from "./components/List.vue";
import InputItem from "./components/Input-item.vue";
export default {
	components: {
	appList: List,
	appInputItem: InputItem
	},
	data() {
		return {
			taskArray: []
		}
	},
	methods: {
		addedTask($event) {
			this.taskArray.push($event);
			console.log($event);
		},
		passedId(id) {
			const index = this.taskArray.findIndex( elem => elem.id === id);

			if (index !== -1) {
				this.taskArray[index].done = !this.taskArray[index].done;
			} 
			
		},
		deleteTask(id) {
			const index = this.taskArray.findIndex( elem => elem.id === id);

			if (index !== -1) {
				this.taskArray.splice(index, 1);
			} 
		}
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
