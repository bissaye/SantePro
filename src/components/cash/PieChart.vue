<template>
  <div>
    <Chart type="pie" :data="chartData" :options="lightOptions" />
  </div>
</template>

<script setup>
import { toRefs } from "@vue/reactivity";
import Chart from "primevue/chart";

import { defineProps } from "vue";

const props = defineProps({
  chartData: {
    type: Object,
    required: true,
  },
  lightOptions: {
    type: Object,
    required: true,
  },
});

const { chartData, lightOptions } = toRefs(props);
</script>
