<template>
    <ul>
        <li v-for="(tarefa, index) in tarefas" :key="index" :class="{'removed': tarefa.feito}">
          <input v-model="tarefa.feito" type="checkbox"> 
          <label>{{tarefa.titulo}}</label>
          <button class="btn btn-outline-secondary" @click="Remover(index)">Remover</button>
        </li>
    </ul>
</template>

<script>
export default {
    props:{
      tarefas: {
        type: Array,
        default(){
          return [
            {titulo: "Lista Vazia" ,checked:false}
          ];
        }
      }
    },
    methods:{
        Remover(index) {
      this.tarefas.splice(index, 1);
    },
    }
}
</script>

<style scoped>
button{
  margin-left:10px;
  margin-bottom: 5px;
}
</style>
