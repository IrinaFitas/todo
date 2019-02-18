<template>
        <ul>
            <app-list-item></app-list-item>
        </ul>
</template>

<script>
import ListItem from "./List-item.vue";
export default {
    data() {
        return {
            
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

