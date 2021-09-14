<template>
  <input @keyup="$emit('retorno', valorint)"  type="text" v-model="valorint">
</template>

<script>
export default {
    props:["valor"],
    data(){
        return{
            valorint : this.valor
        };
    },
};
</script>

<style>

</style>