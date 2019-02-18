<template>
    <li>
        <span :class="{done: doneClass }"> {{ taskFromParent.text }} </span>
        <button class="btn btn-done" @click="taskDone">&#10003;</button>
        <button class="btn btn-delete" @click="taskDeleted">&times;</button>
    </li>
</template>

<script>
export default {
    props: ["taskFromParent"],
    computed: {
        doneClass () {
            if (this.taskFromParent.done) {
                return true;
            } else {
                return false;
            }
        }
    },
    methods: {
        taskDone() {
            this.$emit("taskWasDone", this.taskFromParent.id);
        },
        taskDeleted () {
            this.$emit("taskWasDeleted", this.taskFromParent.id);
        }
    }
}
</script>

<style scoped>
    .done {
        text-decoration: line-through;
    }
</style>


