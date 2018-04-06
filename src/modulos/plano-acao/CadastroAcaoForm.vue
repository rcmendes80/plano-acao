<template>
  <section class="container" id="app">
    <section class="section">
      <div class="field">
        <label class="label">Processo/Modelo</label>
        <div class="control">
          <div class="select is-rounded">
            <select v-model="itemEmEdicao.processo">
              <option disabled>Selecione uma opção</option>
              <option  v-for="processo in processos" :value="processo" :key="processo.id">
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
              <option  v-for="tema in temas" :value="tema" :key="tema.id">
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
              <option  v-for="grupo in grupos" :value="grupo" :key="grupo.id">
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
              <option  v-for="item in itens_observaveis" :value="item" :key="item.id">
                {{item.nome}}
              </option>
            </select>
          </div>
        </div> 
      </div>
      <div class="field">
        <label class="label">Ação</label>
        <div class="control">
          <input class="input" type="text" placeholder="Descreva a ação" v-model="itemEmEdicao.acao" >
        </div>
        <p class="help">This is a help text</p>
      </div>
      <div class="field is-grouped">
        <div class="control">
          <button class="button is-link" @click="addAcao">Adicionar</button>
        </div>
        <div class="control">
          <button class="button is-text">Cancelar</button>
        </div>
      </div>
    </section>
    <section>
      <table class="table">
        <thead>
          <tr>
            <th>&nbsp;</th>
            <th><abbr title="Número">No</abbr></th>
            <th><abbr title="Processo">Processo</abbr></th>
            <th><abbr title="Tema">Tema</abbr></th>
            <th><abbr title="Grupo">Grupo</abbr></th>
            <th><abbr title="Item Observável">Item Observável</abbr></th>
            <th><abbr title="Ação">Ação</abbr></th>
          </tr>
        </thead>
        <!--
        <tfoot>
          <tr>
            <th>Qualification or relegation</th>
          </tr>
        </tfoot>
        -->
        <tbody>
          <tr v-for="(acao, index) in lista_acoes">
            <th><input type="checkbox" :value="index" v-model="lista_acoes_selecionadas"/></th>
             <th>{{index}}</th>
            <td>{{acao.processo.nome}}</td>
            <td>{{acao.tema.nome}}</td>
            <td>{{acao.grupo.nome}}</td>
            <td>{{acao.item.nome}}</td>
            <td>{{acao.acao}}</td>
            
            <td>---</td>
          </tr>
         </tbody>
      </table>
    </section>
  </section>
</template>

<script>


export default {
  name: "CadastroAcaoForm",
  data() {
    return {
      itemEmEdicao: {
        processo: {},
        tema: {},
        grupo: {},
        item: {},
        acao: ''
      },
      lista_acoes_selecionadas:[],
      processos: processos,
      temas: temas,
      grupos: grupos,
      itens_observaveis,
      lista_acoes : []
    };
  },
  methods : {
    addAcao (event) {
      console.log('Adicionado!!!', JSON.stringify(this.itemEmEdicao));
      event.preventDefault();
      this.lista_acoes.push(this.itemEmEdicao);
      this.itemEmEdicao = [];
      
    }
  }
};

const processos = [
  { id: 1, nome: "Gestão de Produtos" },
  { id: 2, nome: "Monitoração e Incidentes" }
];

const temas = [{ id: 1, nome: "Análise Proativa" }];

const grupos = [
  { id: 1, nome: "Cliente" },
  { id: 2, nome: "Novidades" },
  { id: 3, nome: "Roadmap" },
  { id: 4, nome: "Riscos" },
  { id: 5, nome: "Análise da Concorrência" },
  { id: 6, nome: "Níveis de Serviço" },
  { id: 7, nome: "Custos" },
  { id: 8, nome: "Faturamento" },
  { id: 9, nome: "Consumo" }
];

const itens_observaveis = [
  {
    id: 1,
    nome:
      "Cliente com contrato assinado possui data contratação e Valor contratado"
  },
  { id: 2, nome: "Novidades do mês corrente atualizadas" },
  {
    id: 3,
    nome:
      "Todas as funcionalidades estão ancoradas em pelo menos uma motivação "
  },
  {
    id: 4,
    nome:
      "Todos os riscos levantados possuem análise atualizada e ação preenchida"
  },
  {
    id: 5,
    nome:
      "Os concorrentes lançaram novas funcionalidades ou apareceu algum outro concorrente"
  }
];
</script>

<style scopped>
  .column {
    float: left;
  }
</style>
