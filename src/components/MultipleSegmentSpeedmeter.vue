<template>
    <VueSpeedometer
        :value="currentValue"
        :min-value="0"
        :max-value="1000"
        :segments="20"
        :needle-color="'black'"
        :start-color="'green'"
        :end-color="'red'"
        :ring-width="50"
        :text-color="'black'"
        :segment-colors="['#00FF00', '#FFFF00', '#FF0000']"
        :label="'Detailed Speedometer'"
        :needle-height-ratio="0.7"
        :custom-segment-stops="[0, 500, 800, 1000]"
        :max-segment-label="'Overdrive'"
        :current-value-text="`Current Speed: ${currentValue}`"
    />
</template>

<script setup>
import { ref } from 'vue';
import VueSpeedometer from 'vue-speedometer';

const currentValue = ref(750); // Valor inicial del velocímetro
</script>
