<template>
  <div>
    <h1 class="title">History</h1>
    <div class="movements" v-for="movement in movements" :key="movement.id">
      <movement :movement="movement" @remove="remove" />
    </div>
  </div>
</template>

<script setup>
import { toRefs, defineProps } from "vue";
import Movement from "./Movement.vue";

const props = defineProps({
  movements: {
    type: Array,
    default: () => [],
  },
});

const { movements } = toRefs(props);

const remove = (movementId) => {
  console.log(movementId);
};
</script>

<style scoped>
.movements {
  max-height: 100%;
  padding: 0 8px;
  margin-bottom: 14px;
}
.title {
  margin: 8px 16px 24px 16px;
  color: var(--brand-blue);
}
.content {
  max-height: 68vh;
  display: flex;
  flex-direction: column;
  gap: 8px;
  overflow-y: scroll;
}
</style>
