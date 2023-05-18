<template>{{ movement.title }}</template>

<script setup>
import { toRefs, defineProps } from "vue";

const props = defineProps({
  movement: {
    type: Object,
    default: null,
  },
});

const { movement } = toRefs(props);
</script>
