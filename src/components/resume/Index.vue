<template>
  <div>
    <p>{{ labelToShow }}</p>
    <h1>{{ amountToShow }}</h1>
  </div>
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      default: null,
    },
    amount: {
      type: Number,
      default: null,
    },
    totalAmount: {
      type: Number,
    },
  },
  computed: {
    amountToShow() {
      return this.amount !== null ? this.amount : this.totalAmount;
    },
    labelToShow() {
      return this.label !== null ? this.label : "Total saving";
    },
  },
};
</script>

<style scoped>
main {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 100%;
}
h1,
p {
  margin: 0;
  text-align: center;
}
h1 {
  margin-top: 14px;
  color: var(--brand-green);
}
.graphic {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  padding: 48px 24px;
  box-sizing: border-box;
}
</style>
