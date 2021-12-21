<template>
  <div>
    <h3>setup的调用</h3>
    <button @click="aPlus">增加a的值</button>
  </div>
</template>

<script>
import { ref, watch, computed } from "vue";
export default {
  props: ["value"],
  //setup的调用在data,computed,methods,created被解析之前
  setup(props) {
    let abs = props.value + "return";
    // onMounted() ,setup中也有生命周期,名称是加上on

    //computed属性
    console.log("computed属性:");
    let a = ref(0);
    a.value++;
    let b = computed(() => a.value * 2);
    console.log(a.value);
    console.log(b.value);
    return {
      //return的内容可以在其他地方调用
      //可以return值/方法等
      abs,
    };
  },
  created() {
    console.log("setup returen的值:" + this.abs);
  },
  mounted() {},
  watch: {},
  methods: {
    //监听的写法
    aPlus() {
      const a = ref(0);
      a.value = 10;
      watch(a, (newVal, oldVal) => {
        console.log("watch属性:");
        console.log(newVal, oldVal);
      });
      // ???为什么监听没有生效呢???
    },
  },
};
// ref和toRef的区别
// (1). ref本质是拷贝，修改响应式数据不会影响原始数据；toRef的本质是引用关系，修改响应式数据会影响原始数据
// (2). ref数据发生改变，界面会自动更新；toRef当数据发生改变是，界面不会自动更新
// (3). toRef传参与ref不同；toRef接收两个参数，第一个参数是哪个对象，第二个参数是对象的哪个属性

// toRefs
// 用于批量设置多个数据为响应式数据。(toRef一次仅能设置一个数据)
// toRefs接收一个对象作为参数，它会遍历对象身上的所有属性，然后挨个调用toRef执行
</script>

<style>
</style>