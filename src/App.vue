<template>
  <Setup value="'试试setup'" />
  <DivMargin title="以上为setup" />
  <Tele />
  <DivMargin title="以上为teleport,注释了" />
  <TestEmit @childClick="childClick" />
  <DivMargin title="以上为emit" />
</template>

<script>
//引入nextTick
// import { nextTick } from "vue";
import Setup from "./components/setup.vue";
import Tele from "./components/teleportExample.vue";
import DivMargin from "./components/divMargin.vue";
import TestEmit from "./components/testEmit.vue";

export default {
  name: "App",
  components: {
    Setup,
    Tele,
    DivMargin,
    TestEmit,
  },
  methods: {
    childClick() {
      console.log("123");
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
</style>
