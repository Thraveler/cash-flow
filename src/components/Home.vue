<template>
  <layout>
    <template #header>
      <v-header />
    </template>
    <template #resume>
      <resume />
    </template>
    <template #movements>
      <movements />
    </template>
  </layout>
</template>

<script>
import Layout from "@/components/Layout.vue";
import VHeader from "@/components/VHeader.vue";
import Resume from "@/components/resume/Index.vue";
import Movements from "@/components/Movements.vue";

export default {
  components: {
    Layout,
    VHeader,
    Resume,
    Movements,
  },
};
</script>
