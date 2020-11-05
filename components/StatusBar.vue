<template>
    <view class="StatusBar" :style="{ backgroundColor: color }"></view>
</template>

<script>
export default {
    props: ['color']
}
</script>

<style scoped>
    .StatusBar {
        height: 30px;
    }
</style>