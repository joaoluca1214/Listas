<template>
    <div class="input-group">
        <input class="form-control" type="text" v-model="maispalavra">
        <span class="input-group-btn">
            <button class="btn btn-outline-info" @click="adicionar()">Adicionar</button>
        </span>
    </div>
</template>

<script>
export default {
    data(){
        return{
            maispalavra:"",
        }
    },
    methods:{
        adicionar(){
            this.$emit("adicionar", this.maispalavra);
            this.maispalavra = "";
        },
    }
}
</script>

<style scoped>
input{
    margin-right:10px;
}
</style>