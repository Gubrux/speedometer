<template>
    <VueSpeedometer
        :value="currentValue"
        :min-value="0"
        :max-value="500"
        :segments="15"
        :needle-color="'purple'"
        :start-color="'#33cc33'"
        :end-color="'#cc0000'"
        :ring-width="60"
        :text-color="'black'"
        :label="'Fully Custom Speedometer'"
        :force-render="true"
        :custom-segment-stops="[0, 100, 200, 300, 400, 500]"
        :custom-segment-labels="customLabels"
        :max-segment-label="'MAX'"
        :min-segment-label="'MIN'"
        :current-value-text="`Current Speed: ${currentValue}`"
        :needle-transition="'easeElastic'"
        :needle-transition-duration="5000"
        :needle-height-ratio="0.9"
        :width="400"
        :height="300"
    />
</template>

<script setup>
import { ref } from 'vue';
import VueSpeedometer from 'vue-speedometer';

const currentValue = ref(250);

// Etiquetas personalizadas para cada segmento
const customLabels = [
    { text: 'Very Slow', position: 'OUTSIDE', color: '#00FF00' },
    { text: 'Slow', position: 'OUTSIDE', color: '#FFFF00' },
    { text: 'Normal', position: 'OUTSIDE', color: '#FFA500' },
    { text: 'Fast', position: 'OUTSIDE', color: '#FF4500' },
    { text: 'Very Fast', position: 'OUTSIDE', color: '#FF0000' },
];

// Simulación de valor dinámico
setInterval(() => {
    currentValue.value = Math.floor(Math.random() * 500);
}, 6000);
</script>
