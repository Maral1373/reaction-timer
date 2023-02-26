<template>
    <div>
        <p>Reaction: {{ score }} ms</p>
        <p class="rank">{{ rank }}</p>
    </div>
</template>

<script>

export default {
    props: ["score"],
    data() {
        return {
            rank: null
        }
    },
    mounted() {
        if (this.score < 250) {
            this.rank = "Good job"
        }
        else if (this.score < 400) {
            this.rank = "Nice"
        }
        else {
            this.rank = "You!! Snail!!"
        }
    }
}

</script>
<style>
.rank {
    font-size: 1.4rem;
    color: #739f93;
    font-weight: bold;
}
</style>
