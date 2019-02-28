<template>
    <li class="list-item">
        <button class="btn btn-done" @click="taskDone">&#10003;</button>
        <span class="task-text" :class="{done: doneClass }"> {{ taskFromParent.text }} </span>
        <svg 
            xmlns="http://www.w3.org/2000/svg"
            xmlns:xlink="http://www.w3.org/1999/xlink"
            viewBox="0 0 20 20" 
            class="btn-delete" 
            @click="taskDeleted">
            <path fill-rule="evenodd"  fill="rgb(200, 202, 206)"
            d="M10.000,3.000 L10.000,11.000 C10.000,11.552 9.597,12.000 9.100,12.000 L9.000,12.000 L2.000,12.000 L1.900,12.000 C1.403,12.000 1.000,11.552 1.000,11.000 L1.000,3.000 L0.000,3.000 L0.000,2.000 L1.000,2.000 L1.900,2.000 L2.000,2.000 L2.000,1.000 L2.000,-0.000 L3.000,-0.000 L8.000,-0.000 L9.000,-0.000 L9.000,1.000 L9.000,2.000 L9.100,2.000 L10.000,2.000 L11.000,2.000 L11.000,3.000 L10.000,3.000 ZM5.000,10.000 L6.000,10.000 L6.000,4.000 L5.000,4.000 L5.000,10.000 ZM3.000,10.000 L4.000,10.000 L4.000,4.000 L3.000,4.000 L3.000,10.000 ZM8.000,1.000 L3.000,1.000 L3.000,2.000 L8.000,2.000 L8.000,1.000 ZM8.000,4.000 L7.000,4.000 L7.000,10.000 L8.000,10.000 L8.000,4.000 Z"/>
        </svg>
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

    .list-item {
        display: flex;
        align-items: center;
        font-size: 16px;
        width: 100%;
        word-break: break-word;
        border-bottom: 1.5px solid #e6ebed;
    }

    .task-text {
        margin-left: 20px;
        padding: 5px;
        margin-right: 20px;
        line-height: 1.5;
    }
    .btn-done {
        width: 40px;
        flex: none;
        color: #d7d8da;
        height: 40px;
        margin-left: 20px;
        margin-right: 20px;
        border: 1.5px solid #6bb3ca;
        background-color: transparent;
        position: relative;
    }

    .btn-done:hover {
        color: black;
    }
    .btn-delete {
        margin-left: auto;
        padding-top: 10px;
        box-sizing: border-box;
        width: 40px;
        height: 40px;
        overflow: visible;
        display: none;
    }

    .list-item:hover .btn-delete {
        display: block;
    }
</style>


