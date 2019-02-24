<template>
    <div>
        <input type="text" v-model="task">
        <button class="add-btn" @click="addTask">Add</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            task: ""
        }
    },
    methods: {
        addTask() {
            this.$emit("addedTask", { 
                text: this.task,
				id: Date.now(),
                done: false,
            });
            this.task = "";
        }
    }
}
</script>

<style>
    input, .add-btn {
        font-size: 18px;
        border: 1px solid #d1cfcf;
	    box-shadow: 0 0 1px 0 grey;
        padding: 10px;
        margin-bottom: 15px;
    }

    .add-btn {
        background-color: transparent;
        padding: 10px 25px;
        font-weight: bold;
        border-left: none;
        color: white;
        text-transform: uppercase;
        background-color: #d1cfcf;
        cursor: pointer;
    }
</style>

