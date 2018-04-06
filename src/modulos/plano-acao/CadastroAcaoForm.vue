<template>
  <section class="section" id="app">
    <div class="field">
      <label class="label">Processo/Modelo</label>
      <div class="control">
        <div class="select is-rounded">
          <select v-model="itemEmEdicao.processo">
            <option disabled>Selecione uma opção</option>
            <option  v-for="processo in processos" :value="processo">
              {{processo.nome}}
            </option>
          </select>
        </div>
      </div>
    </div>
    <div class="field">
      <label class="label">Tema</label>
      <div class="control">
        <div class="select is-rounded">
          <select v-model="itemEmEdicao.tema">
            <option disabled>Selecione uma opção</option>
            <option  v-for="tema in temas" :value="tema">
              {{tema.nome}}
            </option>
          </select>
        </div>
      </div>
    </div>
    <div class="field">
      <label class="label">Grupo</label>
      <div class="control">
        <div class="select is-rounded">
          <select v-model="itemEmEdicao.grupo">
            <option disabled>Selecione uma opção</option>
            <option  v-for="grupo in grupos" :value="grupo">
              {{grupo.nome}}
            </option>
          </select>
        </div>
      </div> 
    </div>
    <div class="field">
      <label class="label">Item Observável</label>
      <div class="control">
        <div class="select is-rounded">
          <select v-model="itemEmEdicao.item">
            <option disabled>Selecione uma opção</option>
            <option  v-for="item in itens_observaveis" :value="item">
              {{item.nome}}
            </option>
          </select>
        </div>
      </div> 
    </div>
    <div class="field">
      <label class="label">Ação</label>
      <div class="control">
        <input class="input" type="text" placeholder="">
      </div>
      <p class="help">This is a help text</p>
    </div>
  </section>
</template>

<script>

const processos = [
  {id:1, nome:'Gestão de Produtos'},
  {id:2, nome:'Monitoração e Incidentes'},
]

const temas = [
  {id:1, nome:'Análise Proativa'}
]

const grupos = [
  {id:1, nome:'Cliente'},
  {id:2, nome:'Novidades'},
  {id:3, nome:'Roadmap'},
  {id:4, nome:'Riscos'},
  {id:5, nome:'Análise da Concorrência'},
  {id:6, nome:'Níveis de Serviço'},
  {id:7, nome:'Custos'},
  {id:8, nome:'Faturamento'},
  {id:9, nome:'Consumo'}
]

const itens_observaveis = [
  {id:1, nome:'Cliente com contrato assinado possui data contratação e Valor contratado'},
  {id:2, nome:'Novidades do mês corrente atualizadas'},
  {id:3, nome:'Todas as funcionalidades estão ancoradas em pelo menos uma motivação '},
  {id:4, nome:'Todos os riscos levantados possuem análise atualizada e ação preenchida'},
  {id:5, nome:'Os concorrentes lançaram novas funcionalidades ou apareceu algum outro concorrente'},
]

export default {
  name: "CadastroAcaoForm",
  data() {
    return {
      itemEmEdicao : {
        processo : {},
        tema : {},
        grupo : {},
        item: {}
      },
      processos:processos,
      temas:temas,
      grupos: grupos,
    };
  }
};
</script>

<style>

</style>
