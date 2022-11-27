<template>
    <div id="container">
        <div class="card bg-element"></div>
        <div class="card bg-element"></div>
        <div class="card bg-element"></div>
        <div class="card bg-element"></div>
        <div class="card bg-element"></div>

        <div class="card bg-element"></div>
        <div class="card bg-element"></div>
        <div class="card bg-element"></div>
        <div class="card bg-element"></div>
        <div class="card bg-element"></div>

    </div>
</template>

<script>
    export default {
        name: 'MainComp'
    }
</script>

<style lang="scss" scoped>
    #container{
        width: 75%;
        height: calc( 100% - 90px );
        margin: auto;
        padding: 40px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        flex-wrap: wrap;
    }

    .card{
        width: calc(100% / 5 - (10px));
        height: 300px;
    }
</style>