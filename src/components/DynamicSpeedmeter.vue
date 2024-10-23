<template>
    <VueSpeedometer
        :value="currentValue"
        :min-value="0"
        :max-value="200"
        :needle-color="'blue'"
        :start-color="'lightgreen'"
        :end-color="'red'"
        :segments="5"
        :ring-width="40"
        :text-color="'gray'"
        :label="'Basic Speedometer'"
    />
</template>

<script setup>
import { ref } from 'vue';
import VueSpeedometer from 'vue-speedometer';

const currentValue = ref(120);
</script>
