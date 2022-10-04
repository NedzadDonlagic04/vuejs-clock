<script>
export default {

}
</script>

<template>
    <div class="ball"></div>
    <div class="leg hour"></div>
    <div class="leg minute"></div>
    <div class="leg second"></div>
</template>

<style scoped>
    .ball {
        width: 15px;
        height: 15px;
        background-color: black;
        border-radius: 50%;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }

    .leg {
        width: 5px;
        height: 100px;
        background-color: black;
        border-radius: 15px;
        position: absolute;
        top: 50%;
        left: 50%;
        transform-origin: top;
        transform: translate(-50%, -100%);
        transform: rotate(-135deg);
    }

    .hour {
        height: 60px;
        transform: rotate(-45deg);
    }

    .minute {
        height: 90px;
        transform: rotate(-90deg);
    }
</style>