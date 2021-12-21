<template>
  <div class="margindiv">
    <h3>{{ this.title }}</h3>
  </div>
</template>

<script>
export default {
  props: ["title"],
};
</script>

<style>
.margindiv {
  height: 30px;
  width: 100%;
  margin: 10px 0 10px;
  background: lightblue;
}
</style>