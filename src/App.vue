<script>
export default {
    mounted() {
        this.updateClock();
        setInterval(this.updateClock, 1000);
    },
    data() {
        return {
            date: new Date()
        }
    },
    methods: {
        updateClock() {
            this.date = new Date();
        }
    },
    computed: {
        getHours() {
            const hours = this.date.getHours();

            if(hours >= 12)
            {
                hours -= 12;
            }

            const degPerHour = 360 / 12;
            const degOffset = -180;

            const hoursDeg = degPerHour * hours + degOffset;

            return `rotate(${hoursDeg}deg)`;
        },
        getMinutes() {
            const minutes = this.date.getMinutes();

            const degPerMinute = 360 / 60;
            const degOffset = -180;

            const minutesDeg = degPerMinute * minutes + degOffset;

            return `rotate(${minutesDeg}deg)`;
        },
        getSeconds() {
            const seconds = this.date.getSeconds();

            const degPerSecond = 360 / 60;
            const degOffset = -180;

            const secondsDeg = degPerSecond * seconds + degOffset;

            return`rotate(${secondsDeg}deg)`;
        }
    }
}
</script>

<template>
    <div class="ball"></div>
    <div class="leg hour" :style="{ transform: getHours}"></div>
    <div class="leg minute" :style="{ transform: getMinutes}"></div>
    <div class="leg second" :style="{ transform: getSeconds}"></div>
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