<!--Author:steam-404-->
<script>
export default {
    data() {
        return {
            count: 0,
        }
    },
    methods: {
        append() {
            this.count += 1;
        }
    }
}
</script>

<template>
    <button @click="append()">{{ count }}</button>
</template>

<style>

</style>