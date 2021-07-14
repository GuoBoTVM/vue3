<template>
  <div>setup的调用</div>
</template>

<script>
export default {
  props: ["value"],
  methods: {},
  setup(props) {
    console.log(props.value);
    //setup的调用在data,computed,methods,created被解析之前
  },
  created(){
    console.log("123")
  },
};
</script>

<style>
</style>