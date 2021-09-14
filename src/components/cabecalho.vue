<template>
  <header>
      <h1>{{valor}}</h1>
  </header>
</template>

<script>
export default {
  props:["valor"]
}
</script>

<style scoped>
header{
  background-color: aqua;
  position: fixed;
  text-align: center;
  width: 100%;
  height: 50px;
  top: 0;

}
</style>