<template>
	<div id="app">
		<h1>Todo List</h1>
		<app-input-item @addedTask="addedTask"></app-input-item>
		<app-list 
			:list="taskArray" 
			@idWasPassed="passedId" 
			@deleteTaskId="deleteTask"
			:offsetList="offset"
			:limitList="limit"></app-list>
		<app-footer
			:offset="offset"
			:limit="limit"
			:totalItems="taskArray.length"
			@showPrev="offset -= 5"
			@showNext="offset += 5">
		</app-footer>
	</div>
</template>

<script>
import List from "./components/List.vue";
import InputItem from "./components/Input-item.vue";
import FooterList from "./components/Footer-List.vue";
export default {
	components: {
	appList: List,
	appInputItem: InputItem,
	appFooter: FooterList
	},
	data() {
		return {
			taskArray: [],
			offset: 0,
            limit: 5
		}
	},
	methods: {
		addedTask(data) {
			this.taskArray.push(data);
			if (this.taskArray.length % 5 === 0) {
				this.offset += 5;
			}
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
body {
	background-image: linear-gradient(to left, #f6f3f3,#f2eeee);
}
#app {
	margin: auto;
	font-family: 'Avenir', Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
	width: 400px;
	background-color: #ffffff;
	border: 1px solid #d1cfcf;
	box-shadow: 0 0 1px 0 grey;
}
</style>
