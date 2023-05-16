<template>
  <layout>
    <template #header>
      <v-header />
    </template>
    <template #resume>
      <resume :label="label" :totalAmount="10000" :amount="amount" />
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
  data() {
    return {
      label: null,
      amount: null,
    };
  },
};
</script>
