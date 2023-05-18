<template>
  <layout>
    <template #header>
      <v-header />
    </template>
    <template #resume>
      <resume :label="label" :totalAmount="10000" :amount="amount">
        <template #graphic>Graphic</template>
        <template #action>
          <action />
        </template>
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
import Action from "@/components/Action.vue";

export default {
  components: {
    Layout,
    VHeader,
    Resume,
    Movements,
    Action,
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
          amount: 1000,
        },
        {
          id: 1,
          title: "Movement title 2",
          description: "Movement description",
          amount: -500,
        },
        {
          id: 2,
          title: "Movement title 3",
          description: "Movement description",
          amount: 1000,
        },
        {
          id: 3,
          title: "Movement title 4",
          description: "Movement description",
          amount: -23,
        },
        {
          id: 4,
          title: "Movement title 5",
          description: "Movement description",
          amount: 150,
        },
        {
          id: 5,
          title: "Movement title 6",
          description: "Movement description",
          amount: 289,
        },
        {
          id: 6,
          title: "Movement title 7",
          description: "Movement description",
          amount: 1000,
        },
        {
          id: 7,
          title: "Movement title 8",
          description: "Movement description",
          amount: -4000,
        },
        {
          id: 8,
          title: "Movement title 9",
          description: "Movement description",
          amount: 1000,
        },
        {
          id: 9,
          title: "Movement title 10",
          description: "Movement description",
          amount: 1000,
        },
        {
          id: 10,
          title: "Movement title 11",
          description: "Movement description",
          amount: 1000,
        },
        {
          id: 11,
          title: "Movement title 12",
          description: "Movement description",
          amount: 1000,
        },
      ],
    };
  },
};
</script>
