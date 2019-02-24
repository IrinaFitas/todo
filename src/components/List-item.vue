<template>
    <li>
        <button class="btn btn-done" @click="taskDone">&#10003;</button>
        <span :class="{done: doneClass }"> {{ taskFromParent.text }} </span>
        <!-- <button class="btn btn-delete" @click="taskDeleted">&times;</button> -->
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

    li {
        display: flex;
        align-items: center;
        font-size: 16px;
        width: 100%;
        word-break: break-word;
        border-bottom: 1.5px solid #e6ebed;
    }

    span {
        margin-left: 20px;
        padding: 5px;
        margin-right: 20px;
        line-height: 1.5;
    }
    .btn-done {
        width: 40px;
        flex: none;
        height: 40px;
        margin-left: 20px;
        margin-right: 20px;
        border: 1.5px solid #6bb3ca;
        background-color: transparent;
        position: relative;
    }
</style>


