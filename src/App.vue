<template>
    <h1>normal</h1>
    <GaugeChartSpeedmeter />
    <h1>DynamicSpeedmeter</h1>
    <DynamicSpeedmeter />
    <h1>Multiple Segment Speedometer</h1>
    <MultipleSegmentSpeedmeter />
    <h1>Transition</h1>
    <TransitionSpeedmeter />
</template>

<script setup lang="ts">
//@ts-ignore
import DynamicSpeedmeter from './components/DynamicSpeedmeter.vue';
//@ts-ignore
import GaugeChartSpeedmeter from './components/GaugeChartSpeedmeter.vue';
//@ts-ignore
import MultipleSegmentSpeedmeter from './components/MultipleSegmentSpeedmeter.vue';
//@ts-ignore
import TransitionSpeedmeter from './components/TransitionSpeedmeter.vue';
</script>

<style scoped>
.logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
}
.logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
    filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
