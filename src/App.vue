<template>
<section>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
  <cabecalho :valor="titulo"/>
  <br>
  <div class="container">
    <br>
    <h4>Digite o nome do item e clique em adicionar para entrar na lista</h4>
    <adicionar v-on:adicionar="adicionar" />
    <br>
    <lista :tarefas="tarefas"/>
    <em>Total de Tarefas:</em> <span>{{total}}</span>
      <br>
    <em>Tarefas Concluidas:</em> <span>{{concluidas}}</span>
    <hr>
    <footer>
      <em>Edite o Nome da Sua Lista</em>
      <input v-model="titulo" type="text"/>
    </footer>
  </div>
  <br>
  <rodape />
</section> 
</template>

<script>
import cabecalho from "@/components/cabecalho"
import rodape from "@/components/rodape"
import lista from "@/components/lista"
import adicionar from "@/components/adicionar"
export default {
  name: 'App',
  components: {cabecalho , rodape, lista, adicionar},
  data(){
    return{
      titulo: "Minha Lista",
      tarefas:[
        {titulo : "Item concluido", feito: true},
        {titulo : "Item pendente" ,feito: false},
        {titulo : "Clique em Remover para retiraros itens concluidos" ,feito: false},
      ],
    }
  },
  methods: {
    adicionar(maispalavra){
      this.tarefas.push({
        titulo: maispalavra,
        feito:false
      })
    },
    Remover(index) {
      this.tarefas.splice(index, 1);
    },
  },
  computed:{
    total(){
      return this.tarefas.length
    },
    concluidas(){
      return this.tarefas.filter(tarefa => tarefa.feito).length
    }
  }
}
</script>

<style>
.container{
  width: 20%;
  margin: 20px auto 0px;
}
ul li {
    list-style-type: none;
}

.removed{
    color: red;

}

.removed label{
    text-decoration: line-through;
}

</style>
