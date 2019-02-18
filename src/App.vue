<template>
	<div id="app">
		<app-input-item @addedTask="addedTask"></app-input-item>
		<app-list :list="taskArray"></app-list>
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
			taskArray: [
                { id: 1, text: "To do something", done: false },
                { id: 2, text:  "and another task", done: false },
                { id: 3, text:  "...and some another task", done: false },
                { id: 43123948712938, text:  "...and some another task", done: false }
            ]
		}
	},
	methods: {
		addedTask($event) {
			this.taskArray.push($event);
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
