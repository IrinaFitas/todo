<template>
    <footer class="footer-list">
        <button class="btn previous-btn" :disabled="!offset" @click="previous">Previous</button>
        <button class="btn next-btn" :disabled="offset + limit > totalItems" @click="next">Next</button>
    </footer>
</template>
<script>
export default {
    props: ["offset", "limit", "totalItems"],
    methods: {
        previous() {
            this.$emit("showPrev");
        },
        next() {
            this.$emit("showNext");
        }
    }
}
</script>
<style lang="scss" scoped>
    .footer-list {
        display: flex;
        padding: 15px;
        justify-content: space-around;

        button {
            background-color: transparent;
            color: #676f7f;
            font-size: 16px;
            padding: 5px;
            border: none;
            position: relative;
            outline: none;
            cursor: pointer;
        }
    }
    button[disabled] {
        color: #d7d8da;
    }
    .previous-btn::before,
    .previous-btn::after,
    .next-btn::before, 
    .next-btn::after {
        display: inline-block;
        content: "";
        position: absolute;
    } 
    .previous-btn::before {
        border: 10px solid transparent;
        border-right-color: white;
        border-left: 0;
        left: -22px;
        top: 4px;
        z-index: 10;
    }

    .previous-btn::after,
    .next-btn::after {
        width: 25px;
        height: 25px;
        background-color: #676f7f;
        border-radius: 50%;
    }

    .previous-btn::after {
        left: -28px;
        top: 2px;
    }

    .next-btn::before {
        border: 10px solid transparent;
        border-left-color: white;
        border-right: 0;
        right: -22px;
        top: 4px;
        z-index: 10;
    } 

    .next-btn::after {
        right: -28px;
        top: 2px;
    }

    .previous-btn[disabled]::after,
    .next-btn[disabled]::after {
        background-color: #d7d8da;
    }
</style>

