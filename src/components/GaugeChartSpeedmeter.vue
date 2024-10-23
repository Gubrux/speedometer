<template>
    <VueSpeedometer
        :value="currentValue"
        :min-value="0"
        :max-value="1000"
        :segments="10"
        :needle-color="'red'"
        :start-color="'green'"
        :end-color="'red'"
        :ring-width="30"
        :text-color="'black'"
        :label="'Custom Speed'"
    />
</template>

<script setup>
import { ref } from 'vue';
import VueSpeedometer from 'vue-speedometer';

const currentValue = ref(500);
</script>
