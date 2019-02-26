<template>
    <footer class="footer-list">
        <button class="previous-btn">Previous</button>
        <button class="next-btn">Next</button>
    </footer>
</template>
<script>
export default {
    
}
</script>
<style>
    .footer-list {
        display: flex;
        padding: 15px;
        justify-content: space-around;
    }

    button {
        background-color: transparent;
        color: #d7d8da;
        font-size: 16px;
        padding: 5px;
        border: none;
        position: relative;
    }   
    .previous-btn::before {
        display: inline-block;
        content: "";
        border: 10px solid transparent;
        border-right-color: white;
        border-left: 0;
        position: absolute;
        left: -22px;
        top: 4px;
        z-index: 10;
    } 

    .previous-btn::after {
        display: inline-block;
        position: absolute;
        left: -28px;
        top: 2px;
        content: "";
        width: 25px;
        height: 25px;
        background-color: #d7d8da;
        border-radius: 50%;
    }

    .next-btn::before {
        display: inline-block;
        content: "";
        border: 10px solid transparent;
        border-left-color: white;
        border-right: 0;
        position: absolute;
        right: -22px;
        top: 4px;
        z-index: 10;
    } 

    .next-btn::after {
        display: inline-block;
        position: absolute;
        right: -28px;
        top: 2px;
        content: "";
        width: 25px;
        height: 25px;
        background-color: #d7d8da;
        border-radius: 50%;
    }
</style>

