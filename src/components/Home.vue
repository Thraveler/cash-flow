<template>
  <layout>
    <template #header>
      <v-header />
    </template>
    <template #resume>
      <resume :label="label" :totalAmount="10000" :amount="amount">
        <template #graphic>Graphic</template>
        <template #action>Action</template>
      </resume>
    </template>
    <template #movements>
      <movements :movements="movements" />
    </template>
  </layout>
</template>

<script>
import Layout from "@/components/Layout.vue";
import VHeader from "@/components/VHeader.vue";
import Resume from "@/components/resume/Index.vue";
import Movements from "@/components/movements/Index.vue";

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
      movements: [
        {
          id: 0,
          title: "Movement title 1",
          description: "Movement description",
          amoun: 1000,
        },
        {
          id: 1,
          title: "Movement title 2",
          description: "Movement description",
          amoun: 1000,
        },
        {
          id: 2,
          title: "Movement title 3",
          description: "Movement description",
          amoun: 1000,
        },
        {
          id: 3,
          title: "Movement title 4",
          description: "Movement description",
          amoun: 1000,
        },
        {
          id: 4,
          title: "Movement title 5",
          description: "Movement description",
          amoun: 1000,
        },
        {
          id: 5,
          title: "Movement title 6",
          description: "Movement description",
          amoun: 1000,
        },
      ],
    };
  },
};
</script>
