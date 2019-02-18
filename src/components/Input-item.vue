<template>
    <div>
        <input type="text" v-model="task">
        <button @click="addTask">Add</button>
        <p>{{ task }}</p>
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
                done: false
            });
        }
    }
}
</script>

<style>

</style>

