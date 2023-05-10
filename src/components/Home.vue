<template>
  <layout>
    <template #header>
      <v-header />
    </template>
  </layout>
</template>

<script>
import Layout from "@/components/Layout.vue";
import VHeader from "@/components/VHeader.vue";

export default {
  components: {
    Layout,
    VHeader,
  },
};
</script>
