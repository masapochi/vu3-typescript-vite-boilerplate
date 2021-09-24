<script lang="ts">
import { defineComponent, toRefs, reactive } from "@vue/runtime-core";
import HelloWorld from "./components/HelloWorld.vue";

type State = {
  message: string | number;
};

export default defineComponent({
  name: "App",
  components: {
    HelloWorld,
  },
  setup(props, context) {
    const state = reactive<State>({
      message: "Hello Vue 3 + TypeScript + Vite",
    });
    const changeMessage = (message) => {
      state.message = message;
    };

    return { state, changeMessage };
  },
});
</script>

<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <p>{{ message }}</p>
  <HelloWorld :message="state.message" @change-message="changeMessage" />
</template>

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
