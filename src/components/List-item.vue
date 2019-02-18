<template>
    <li>
        <span> {{ taskFromParent.text }} </span>
        <button class="btn btn-done" @click="taskDone">&#10003;</button>
        <button class="btn btn-delete" @click="taskDeleted">&times;</button>
    </li>
</template>

<script>
export default {
    props: ["taskFromParent"],
    methods: {
        taskDone() {
            console.log(this.taskFromParent);
            this.$emit("taskWasDone", this.taskFromParent.id);
        },
        taskDeleted () {

        }
    }
}
</script>

