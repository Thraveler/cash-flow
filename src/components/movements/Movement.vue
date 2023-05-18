<template>
  <div class="movement">
    <div class="content">
      <h4>{{ movement.title }}</h4>
      <p>{{ movement.description }}</p>
    </div>
    <div class="action">
      <img src="@/assets/trash-icon.svg" alt="trash-icon" @click="remove" />
      <p :class="{ green: isPositive, red: !isPositive }">
        {{ formatedCurrency }}
      </p>
    </div>
  </div>
</template>

<script setup>
import currencyFormater from "@/utils/currencyFormater";
import { toRefs, defineProps, defineEmits, computed } from "vue";

const props = defineProps({
  movement: {
    id: {
      type: Number,
    },
    title: {
      type: String,
    },
    description: {
      type: String,
    },
    amount: {
      type: Number,
    },
  },
});

const { movement } = toRefs(props);

const formatedCurrency = currencyFormater.format(movement.value.amount);

const isPositive = computed(() => movement.value.amount > 0);

const emit = defineEmits(["remove"]);

const remove = () => {
  emit("remove", movement.value.id);
};
</script>

<style scoped>
.movement {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  padding: 16px;
  background-color: #e6f9ff;
  border-radius: 8px;
  box-sizing: border-box;
}
.movement .content {
  width: 100%;
}
.movement .action {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  flex-direction: column;
}
h4,
p {
  margin: 0;
  padding: 0;
}
h4 {
  margin-bottom: 8px;
}
.movement .action img {
  margin-bottom: 16px;
}
.red {
  color: red;
}
.green {
  color: green;
}
</style>
