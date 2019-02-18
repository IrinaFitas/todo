<template>
        <ul>
            <transition-group name="list">
                <app-list-item 
                    v-for="(item, index) in list" 
                    :taskFromParent="item" 
                    :key="index"
                    @taskWasDone="addDone"
                    @taskWasDeleted="deleteTask">
                </app-list-item>
            </transition-group>
        </ul>
</template>

<script>
import ListItem from "./List-item.vue";
export default {
    props: ["list"],
    methods: {
        addDone(id) {
            this.$emit("idWasPassed", id);
        },
        deleteTask(id) {
            this.$emit("deleteTaskId", id);
        }
    },
    components: {
        appListItem: ListItem
    }
}
</script>

<style>
    ul {
        list-style: none;
        margin: 0;
        padding: 0;
    }

    .list-item {
        display: inline-block;
        margin-right: 10px;
    }
    .list-enter-active, .list-leave-active {
        transition: all 1s;
    }
    .list-enter, .list-leave-to /* .list-leave-active below version 2.1.8 */ {
        opacity: 0;
        transform: translateY(30px);
    }
</style>

