<template>
        <ul>
            <app-list-item 
                v-for="(item, index) in list" 
                :taskFromParent="item" 
                :key="index"
                @taskWasDone="addDone">
            </app-list-item>
        </ul>
</template>

<script>
import ListItem from "./List-item.vue";
export default {
    props: ["list"],
    methods: {
        addDone(id) {
            //this.taskArray.forEach(elem => );
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
</style>

