<template>
    <div class="block" v-if="showBlock" @click="stopTimer">
        Click Me
    </div>
</template>
<script>
export default {
    props: ["delay"],
    data() {
        return {
            showBlock: false,
            timer: null,
            reactionTimer: 0
        }
    },
    mounted() {
        console.log("Component mounted");
        setTimeout(() => {
            this.showBlock = true
            this.startTimer()
            console.log(this.delay)
        }, this.delay)
    },
    methods: {
        startTimer() {
            this.timer = setInterval(() => {
                this.reactionTimer += 10
            }, 10)
        },
        stopTimer() {
            clearInterval(this.timer)
            console.log(this.reactionTimer)
        }
    }
}
</script>
<style>
.block {
    width: 400px;
    border-radius: 20px;
    background: #739f93;
    color: #f5f5f5;
    font-weight: bold;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
}
</style>