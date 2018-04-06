<template>
  <div id="app">
    <section class="hero is-primary">
      <div class="hero-body">
        <div class="container">
          <h1 class="title">
            Análise de Conformidade > Plano de Ação
          </h1>
          <h2 class="subtitle">
            Acompanhamento e status das ações planejadas
          </h2>
        </div>
      </div>
    </section>
    <cadastro-acao-form></cadastro-acao-form>
  </div>
</template>

<script>
import CadastroAcaoForm from './modulos/plano-acao/CadastroAcaoForm.vue'
export default {
  name: "app",
  components: {
    'cadastro-acao-form' : CadastroAcaoForm,
  },
  data() {
    return {
      msg: "Welcome to Your Vue.js App"
    };
  }
};
</script>

<style>

</style>
