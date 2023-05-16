<template>
  <main>
    <p>{{ labelToShow }}</p>
    <h1>{{ amountToShow }}</h1>
    <div class="graphic">
      <slot name="graphic"></slot>
    </div>
    <div class="action">
      <slot name="action"></slot>
    </div>
  </main>
</template>

<script>
const currencyFormater = new Intl.NumberFormat("es-MX", {
  style: "currency",
  currency: "MXN",
});

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
      return this.amount !== null
        ? currencyFormater.format(this.amount)
        : currencyFormater.format(this.totalAmount);
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
