<template>
  <Suspense>
    <template #default>
      <home />
    </template>
    <template #fallback>
      <splash-screen />
    </template>
  </Suspense>
</template>

<script>
// import Home from "@/components/Home.vue";
import SplashScreen from "@/components/SplashScreen.vue";
import { defineAsyncComponent } from "vue";

export default {
  name: "App",
  components: {
    Home: defineAsyncComponent(
      () =>
        new Promise((resolve) => {
          setTimeout(() => {
            resolve(import("./components/Home.vue"));
          }, 2000);
        })
    ),
    SplashScreen,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
