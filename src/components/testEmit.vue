<template>
  <div>
    <button @click="testClick(1, 2)">点击</button>
  </div>
</template>

<script>
export default {
  emits: {
    // emit可以像props一样验证, 也可以简单的写为数组
    childClick: ({ a, b }) => {
      if (a && b) {
        return true;
      } else {
        return false;
        // 传递false仍然可以走通emit事件,只不过console打印中有提示
      }
    },
  },
  methods: {
    testClick(a, b) {
      this.$emit("childClick", { a, b });
    },
  },
};
</script>

<style>
</style>