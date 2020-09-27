<template>
    <div class="navbar">
        <h1>Sweepy's</h1>
    </div>
</template>

<script>
    export default {
        name: "Navbar"
    }
</script>

<style lang="scss" scoped>
    .navbar {
        /* background: rgb(2,0,36); */
        /* background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(40,129,186,1) 0%, rgba(0,212,255,1) 100%); */
        /* background: #fff; */
        background: rgb(131,58,180);
        background: linear-gradient(90deg, rgba(131,58,180,1) 0%, rgba(253,29,29,1) 50%, rgba(252,176,69,1) 100%);

        display: flex;
        justify-content: flex-start;
        box-shadow: 2px 2px 5px #e1e2e3;
    }

    .navbar h1 {
        padding: 0 15px;
        color: #fff;
    }
</style>
