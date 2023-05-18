<template>
  <button @click="isModalOpen = true">Add new movement</button>
  <Teleport to="#app">
    <modal v-show="isModalOpen" @close="isModalOpen = false">
      <form @submit.prevent="submit">
        <div class="field">
          <label for="title">Title</label>
          <input type="text" name="title" v-model="title" />
        </div>
        <div class="field">
          <label for="amount">Amount</label>
          <input type="number" name="amount" v-model="amount" />
        </div>
        <div class="field">
          <label for="description">Description</label>
          <input type="text" name="description" v-model="description" />
        </div>
        <div class="field">
          <label class="radio-label" for="income">
            <input
              type="radio"
              name="movementType"
              value="income"
              id="income"
              v-model="movementType"
            />
            Income
          </label>

          <label class="radio-label" for="spent"
            ><input
              type="radio"
              name="movementType"
              value="spent"
              id="spent"
              v-model="movementType"
            />
            Spent
          </label>
        </div>
        <div>
          <button>Add movement</button>
        </div>
      </form>
    </modal>
  </Teleport>
</template>

<script setup>
import Modal from "@/components/Modal.vue";
import { ref } from "vue";

let isModalOpen = ref(false);
let title = ref("");
let amount = ref(0);
let description = ref("");
let movementType = ref("income");

const submit = () => {
  console.log("click");
  isModalOpen.value = false;
};
</script>

<style scoped>
button {
  color: white;
  font-size: 1.25rem;
  background-color: var(--brand-blue);
  border: none;
  width: 100%;
  padding: 24px 60px;
  border-radius: 60px;
  box-sizing: border-box;
}

form {
  font-size: 1.24rem;
  width: 100%;
}

form .action {
  padding: 0 24px;
}

.field {
  display: flex;
  justify-content: space-between;
  flex-direction: column;
  padding: 16px 24px;
}

label {
  margin-bottom: 8px;
}

input,
textarea {
  font-size: 1.24rem;
  border: 2px solid var(--brand-blue);
  border-radius: 8px;
  padding: 8px;
}

input[type="number"] {
  text-align: right;
}

.radio-label {
  display: flex;
  align-items: center;
  margin-top: 8px;
}

.radio-label span {
  margin-top: 4px;
  margin-left: 8px;
}

input[type="radio"] {
  appearance: none;
  width: 1.24rem;
  height: 1.24rem;
  color: var(--brand-blue);
  border: 2px solid var(--brand-blue);
  border-radius: 50%;
}

input[type="radio"]:checked {
  background-color: var(--brand-blue);
}
</style>
