<template>
    <div>
        <input type="text" :value="value">
        <button @click="addTask">Add</button>
    </div>
</template>

<script>
export default {
    props: ["value"],
    methods: {
        addTask() {
            console.log($event);
            this.$emit("input", $event.target.value);
        }
    }
}
</script>

<style>

</style>

