<template>
    <div>
        <ul>
            <li v-for="value in arr"> {{ value }} </li>
        </ul>
    </div>
</template>

<script>
export default {
    data() {
        return {
            arr: [1, 2, 3]
        }
    }
}
</script>

