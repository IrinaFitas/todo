<template>
        <div>
            <transition-group name="list" tag="ul" class="list">
                <app-list-item 
                    v-for="(item, index) in limitedList" 
                    :taskFromParent="item" 
                    :key="index"
                    @taskWasDone="addDone"
                    @taskWasDeleted="deleteTask">
                </app-list-item>
            </transition-group>
        </div>
</template>

<script>
import ListItem from "./List-item.vue";
export default {
    props: ["list", "offsetList", "limitList"],
    computed: {
        limitedList() {
            return this.list.slice(this.offsetList, this.offsetList + this.limitList);
        }
    },
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
    .list {
        list-style: none;
        margin: 0;
        padding: 0;
        width: 100%;
        position: relative;
    }
    .list::before {
        content: "";
        width: 4px;
        height: 100%;
        border-left: 1px solid #f2e3df;
        border-right: 1px solid #f2e3df;
        position: absolute;
        left: 80px;
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

